<template>

    <div class="backg container-fluid">

        <section class="row mySection">

            <div class="col-12 text-center">

               <SelecGenre @selectedOpt="genreMethod" />

            </div>

            <div class="col-12 text-center">
                <SelectArtist :albums="albums" @selectedOpt="authorMethod" />
            </div>

        </section>

        <section class="row mySection" v-if="load == false">
            <div class="albums col-sm-6 col-md-4 my-col-lg-2" v-for="(album, index) in genreFiltredComputed" :key="index">
                <AlbumItem :item="album" />
            </div>
        </section>
        <Loader loadingtext="just a sec featching data" v-else/>
    </div>

</template>

<script>
import AlbumItem from './AlbumItem';
import SelecGenre from './SelecGenre';
import SelectArtist from './SelectArtist';
import Loader from './Loader';
import axios from 'axios';


export default {
    name: "AlbumContainer",
    components: {
        AlbumItem,
        Loader,
        SelecGenre,
        SelectArtist
    },
    data() {
        return {
            api: 'https://flynn.boolean.careers/exercises/api/array/music',
            albums: [],
            load: true,
            userChoice: '',
            authorChoice: ''
        }
    },
    computed: {
        genreFiltredComputed: function(){
            const newAlbum = this.albums.filter(
                (elem) => {

                    if (this.userChoice == "All") {
                        return this.albums
                    }

                    return elem.genre.includes( this.userChoice )
                }
            );
            return newAlbum
        },
        authorFiltred: function() {
            const authorArr = this.albums.filter(
                (element) => {
                    
                    return element.author.includes( this.authorChoice )
                }
            );
            return authorArr
        }
    },
    methods: {
        authorMethod: function(authSon) {
            this.authorChoice = authSon;
        },
        genreMethod: function(fromSon) {
            this.userChoice = fromSon;
        }
        
    },
    created: function() {
        axios.get(this.api).then(
            (resp) => {
                this.albums = resp.data.response;
                // console.log(this.albums); la arrowfunction per lo scope !!!!!!!!
                    this.load = false; 
                // setTimeout( () => {
                //     this.load = false; 
                // }, 500)
            }
        )
        .catch()
    }

}
</script>

<style lang="scss" scoped>
@import "../style/vars.scss";

    .backg {
    background-color: $bg-body;
    }

    .mySection {
    width: 62%;
    padding: 56px 0;
    margin: 0 auto;
    border: 1px solid #fff;
    }
    
    .albums {
        // border: 1px solid #fff;
        margin-bottom: 16px;
    }

    @media screen and (min-width: 1100px) {
        
        .my-col-lg-2 {
          width: calc(100% / 5);
        }
        
    }
</style>
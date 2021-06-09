<template>

    <div class="backg container-fluid">
        <section class="row align-items-center">
            <div class="albums col-sm-6 col-md-4 my-col-lg-2" v-for="(album, index) in albums" :key="index">
                <AlbumItem :item="album" />
            </div>
        </section>
    </div>

</template>

<script>
import AlbumItem from './AlbumItem'
import axios from 'axios'

export default {
    name: "AlbumContainer",
    components: {
        AlbumItem
    },
    data() {
        return {
            api: 'https://flynn.boolean.careers/exercises/api/array/music',
            albums: []
        }
    },
    created: function() {
        axios.get(this.api).then(
            (resp) => {
                this.albums = resp.data.response;
                console.log(this.albums);
            }
        )
    }

}
</script>

<style lang="scss" scoped>
@import "../style/vars.scss";

  .backg {
    background-color: $bg-body;
  }

  // max-width: sectin

  section {
    width: 62%;
    padding: 56px 0;
    margin: 0 auto;
    // display: flex;
    // flex-wrap: wrap;
  }
  .my-col-lg-2 {
      width: calc(100% / 5);
  }

    .albums {
        // border: 1px solid #fff;
        margin-bottom: 16px;
    }
</style>
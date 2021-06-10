<template>
    <select value="authors" id="myAuthors" v-model="selectAuthor" @click="$emit('selectedOpt', selectAuthor)">
        
        <option v-for="(album, index) in albums" :key="index" :value="album.author"> {{ album.author }} </option>
    </select>
</template>

<script>
export default {
    name: "SelectArtist",
    props: ["albums"],
    data() {
        return {
            selectAuthor: ''
        }
    }
}
</script>

<style>

</style>
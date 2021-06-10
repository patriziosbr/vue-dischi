<template>
   <select name="genre" id="myGenre" v-model="slectedGen" @click="$emit('selectedOpt', slectedGen)">
        <option value="All">All</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
    </select>
</template>

<script>
export default {
    name: "SelecGenre",
    data() {
        return {
            slectedGen: 'All',
            options: [
                
            ]
        }
    }
}
</script>

<style>

</style>
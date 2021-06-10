<template>
   <select name="genre" id="myGenre" v-model="slectedGen">
        <option value="All" @click="$emit('selectedOpt', slectedGen)">All</option>
        <option value="Rock" @click="$emit('selectedOpt', slectedGen)" >Rock</option>
        <option value="Pop" @click="$emit('selectedOpt', slectedGen)" >Pop</option>
        <option value="Jazz" @click="$emit('selectedOpt', slectedGen)" >Jazz</option>
        <option value="Metal" @click="$emit('selectedOpt', slectedGen)" >Metal</option>
    </select>
</template>

<script>
export default {
    name: "SelecGenre",
    data() {
        return {
            slectedGen: ''
        }
    }
}
</script>

<style>

</style>
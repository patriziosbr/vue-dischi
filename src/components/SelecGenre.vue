<template>
   <!-- <select name="genre" id="myGenre" v-model="slectedGen" @click="$emit('selectedOpt', slectedGen)">
        <option value="All">All</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
    </select> -->
    <select name="genre" id="myGenre" v-model="slectedGen" @click="$emit('selectedOpt', slectedGen)">
        <option :value="option.value" v-for="(option, index) in options" :key="index"> {{ option.txt }}</option>
    </select>

</template>

<script>
export default {
    name: "SelecGenre",
    data() {
        return {
            slectedGen: 'All',
            options: [
                {
                    txt: "All",
                    value: "All"
                },
                {
                    txt: "Rock",
                    value: "Rock"
                },
                {
                    txt: "Pop",
                    value: "Pop"
                },
                {
                    txt: "Jazz",
                    value: "Jazz"
                },
                {
                    txt: "Metal",
                    value: "Metal"
                }
            ]
        }
    }
}
</script>

<style>

</style>
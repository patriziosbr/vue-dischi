<template>
    <div class="loadcontainer">
        <div class="txt">{{ loadingtext }}</div>
        <div class="txt"> Uploading content </div>
    </div>
</template>

<script>
export default {
    name: "Loader",
    props: [ "loadingtext" ]
}
</script>

<style lang="scss" scoped>

    .loadcontainer {
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        .txt {
            font-size: 24px;
            color: #fff;
        }
    }

</style>
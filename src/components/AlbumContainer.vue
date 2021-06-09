<template>

    <section>
        <div class="albums">
            
        </div>
    </section>

</template>

<script>
export default {
    name: "AlbumContainer"

}
</script>

<style lang="scss" scoped>
@import "../style/vars.scss";

  section {
    height: calc(100vh - 60px);
    background-color: $bg-body;
    display: flex;
    
    
  }

    .albums {
        margin: auto;
        width: 900px;
        height: 500px;
        border: 1px solid #fff;
     
    }
</style>
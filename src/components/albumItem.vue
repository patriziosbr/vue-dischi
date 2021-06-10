<template>
  <div class="discItem img-fluid">
      <img :src="item.poster" alt="">
      <h2>{{ item.title }}</h2>
      <p>{{ item.author }}</p>
      <p>{{ item.year }}</p>
  </div>
</template>

<script>
export default {
    name: "AlbumItem",
    props: [ "item" ]
}
</script>

<style lang="scss" scoped>
@import "../style/vars.scss";

    .discItem {
        width: 180px;
        height: 280px;
        padding: 16px;
        background-color: $bg-header;
        text-align: center;
        img {
            width: 100%;
        }
        h2 {
            font-size: 16px;
            font-weight: 700;
            text-transform: uppercase;
            color: $white;
            margin: 16px 0;
        }
        p {
            color: #ccc;
            margin: 0;
            font-size: 13px;
            line-height: 150%;
        }
    }

   
</style>
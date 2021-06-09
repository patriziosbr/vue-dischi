<template>
  <section>
      <img class="p-1 ms-3" src="../assets/spotify.png" alt="">
  </section>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style lang="scss" scoped>
@import '../style/vars.scss';

    section {
        width: 100%;
        height: 60px;
        background-color: $bg-header;
        img {
            height: 100%;
        }
    }
</style>
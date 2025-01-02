<template>
  <div id="container">
    <p>JV</p>
    <img src="../assets/main-heart.gif" alt="">
    <p>Cams</p>
  </div>
</template>
<script>
export default {
  name: 'Logo',

}
</script>
<style scoped>
  #container{
    display: flex;
    font-family: "Pixelify Sans", serif;
    font-optical-sizing: auto;
    font-style: normal;
    font-size: 60px;
    align-items: center;
    justify-content: center;
  }
  #container img{
    height: 100px;
    padding-right: 10px;
  }
</style>
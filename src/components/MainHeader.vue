<template>
  <div class="nav">
    <div class="logo">
        <img src="./spotify-icon-marilyn-scott-0.png" alt="">
    </div>
  </div>
</template>

<script>
export default {
   name: 'MainHeader',
    props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import './style.scss';
  .nav{
    height: 70px;
    width: 100%;
    background-color: $bg-card;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding-left: 20px;
  }
  .logo{
    img{
      height: 50px;
      width: 50px;
    }
  }

</style>
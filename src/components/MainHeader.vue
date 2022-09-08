<template>
  <div class="nav">
    <div class="logo">
      <img src="./spotify-icon-marilyn-scott-0.png" alt="">
    </div>
    <div class="text-center">
      <select @change="$emit('musicGenre',options)" v-model="options">
        <option default value="">Scegli il Tuo Genere Preferito</option>
        <option value="Pop">Pop</option>
        <option value="Rock">Rock</option>
        <option value="Metal">Metal</option>
        <option value="Jazz">Jazz</option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainHeader',
  props: {
    msg: String
  },
  data() {
    return {
       options:'',
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import './style.scss';

.nav {
  height: 70px;
  width: 100%;
  background-color: $bg-card;
  display: flex;
  justify-content:space-between;
  align-items: center;
  padding-left: 20px;
  padding-right: 20px;
}

.form-select{
    background-color:$Wc--color ;
    color: white;
    font-weight: bold;
  }

.logo {
  img {
    height: 50px;
    width: 50px;
  }
}
</style>
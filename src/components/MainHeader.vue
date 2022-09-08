<template>
  <div class="nav">
    <div class="logo">
      <img src="./spotify-icon-marilyn-scott-0.png" alt="">
    </div>
    <div class="search text-center">
      <select id="mySelect" @change="onChange($event)" v-model="genre">
        <option selected>Scegli il Tuo Genere Preferito</option>
        <option value="pop">Pop</option>
        <option value="rock">Rock</option>
        <option value="metal">Metal</option>
        <option value="jazz">Jazz</option>
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
  methods: {
        onChange(event) {
            console.log(event.target.value)
        }
    }
 
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
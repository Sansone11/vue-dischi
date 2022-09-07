<template>
  <main>
    <div class="card-wrapper ">
      <div class="card " v-for="caracters, i in listMusic" :key="i" style="width: 13rem; ">
        <img :src="caracters.poster" class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title" :title="caracters.title">{{caracters.title}}</h5>
          <p class="card-text">{{caracters.author}}</p>
          <p class="year-text" :class="caracters.year">{{caracters.year}}</p>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      listMusic: []
    }
  },
  created() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        console.log(res.data.response)
        this.listMusic = res.data.response;
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import './style.scss';

main{
  width: 100%;
  background-color: $bg--color ;
  margin: 0 auto;
}

.card-wrapper {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  padding-left: 80px;
  padding-top: 40px;

  .card {
    padding: 1rem;
    margin-bottom: 5rem;
    background-color: $bg-card;
  }

  .card-text {
    color: $Wc--color;
    text-align: center;
  }

  .year-text {
    color: $Wc--color;
    text-align: center;

  }

  .card-title {
    color: white;
  }
}
</style>
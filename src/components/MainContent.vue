<template>
  <main>
    <div class="card-wrapper ">
      <div class="card " v-for="caracters, i in filterGenre" :key="i" style="width: 13rem; ">
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
  props:{
    options:{
      type: String,
        default:'',
    }
       
  },
  data() {
    return {
      listMusic: [],
    }
  },
  created() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        // console.log(res.data.response);
        this.listMusic = res.data.response;
      })
  },
  computed : {
    filterGenre(){
      return this.listMusic.filter((el)=> {
        // console.log(el);
        if(el.genre === this.options || this.options === ''){
          return true
        }
        return false
      });
    }

  },
 

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import './style.scss';

main{
  background-color: $bg--color ;
  margin: 0 auto;
  padding: 40px 200px;
  min-height: 600px;
}

.card-wrapper {
  display: grid;
  grid-template-columns: repeat(5, 1fr);

  .card {
    padding: 1rem;
    background-color: $bg-card;
    margin-bottom: 1rem;
  }

  .card-text {
    color: $Wc--color;
    text-align: center;

  }

  .card-body{
    padding: 2rem;
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
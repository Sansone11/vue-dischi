<template>
  <div>
    <b-card v-for="caracters, i in listMusic" :key="i" :title="caracters.author" :img-src="caracters.poster"
      img-alt="Image" img-top tag="article" style="max-width: 20rem;" class="mb-2">
      <b-card-text>
        {{caracters.author}}
      </b-card-text>

      <b-button href="#" variant="primary">Go somewhere</b-button>
    </b-card>
  </div>
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
        console.log(res.data)
        this.listMusic = res.data;
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
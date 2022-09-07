<template>
  <div>
    <b-card v-for="caracters, i in listMusic" :key="i" :title = "caracters.author" :img-src="carater.poster" img-alt="Image" img-top tag="author"
      style="max-width: 20rem;" class="mb-2">
      <b-card-text>
      </b-card-text>
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
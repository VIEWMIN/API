<template>
 <div class="111">
    <div class="container">
      <div class="row">
        <div class="col col-3">
          <b-card>
            <br>
            <h5> {{ toonList.synopsis }} </h5>
          </b-card>
          <br>
        </div>
        <div class="col col-6">
          <b-card>
            <h3>{{ listdata.title_english }}</h3>
          </b-card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
data() {
    return {
      toonList: "",
      url: `https://api.jikan.moe/v3/manga/${this.$route.params.id}`,
    };
  },
  
  mounted() {
    axios
      .get(this.url)
      .then((response) => {
        this.toonList = response.data;
      })
      .catch((err) => {
        console.log(err);
        alert(err);
      });
  },
}
</script>

<style>

</style>

<template>
  <div>
     <section v-if="!loading">
      <div class="container">
        <div class="row row-cols-5"></div>
        
          <DiskComponent v-for="(item, index) in list" :key="index"
            :img="item.poster"
            :title="item.title"
            :author="item.author"
            :year="item.year"
          />
        
      </div>
    </section>
    <div
      class="d-flex min-vh-100 align-items-center justify-content-center"
      v-else
    >
      <h1>loading ...</h1>
    
    </div>
  </div>

    
  
</template>


<script>

import axios from "axios";
import DiskComponent from "@/components/DiskComponent.vue";

export default {
  name: "DisksList",
  components: {
    DiskComponent,
  },
  data() {
    return {
      API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
      item: null,
      loading: true,
      error:null
    };
  },
  methods: {
    callApi() {
      axios
        .get(this.API_URL)
        .then((response) => {
            console.log(this.list);
          this.list = response.data.response;
          this.loading = false;
        })
        .catch((error) => {
          console.error();
          error;
          this.error = `Sorry There is a problem! ${error}`;
        });
    },
  },
  mounted() {
    this.callApi();
  },
};
</script>





<style lang="scss">
.container{
    height: calc(100vh - 100px);
}

</style>

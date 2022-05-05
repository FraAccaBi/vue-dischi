<template>
  <div>
     <section class="characters" v-if="!loading">
      <div class="container">
        <h1 class="text-center my-3">spotify</h1>
        <div class="row g-3">
          <DiskComponent 
            :album="album"
            v-for="(album, index) in discs"
            :key="index"
          />
        </div>
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
      discs: null,
      loading: true,
      error: null,
    };
  },
  methods: {
    callApi() {
      axios
        .get(this.API_URL)
        .then((response) => {
          this.characters = response.data;
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

</style>

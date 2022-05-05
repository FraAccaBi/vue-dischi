<template>
  <div >
    
    
  </div>
</template>

<script>

import axios from "axios";
export default {
  name: 'SiteMain',
  data() {
    return {
      API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
    };
  },
  components: {},
  methods: {
      callAPI(){
        axios.get(this.API_URL).then((response) => {
        console.log(response);
        this.characters = response.data;
      })
      }
  }
}
</script>

<style lang="scss">

@use '@/assets/scss/style.scss';

</style>
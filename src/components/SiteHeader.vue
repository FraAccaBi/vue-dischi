<template>
  <div class="header" >
    <img class="d-flex justify-content-start p-2" src="../../public/pngwing.png" alt="">
    <div class="search">
      <SearchBox v-model="searchText" @formSubmit="search" />
    </div>
  </div>
  
</template>

<script>

import SearchBox from "@/components/SearchComponent.vue";
import state from "@/state.js";
export default {
  name: 'SiteHeader',
  components:{
    SearchBox,
  },
  data() {
    return {
      searchText: "",
    };
  },
  methods: {
    search() {
      //console.log('Searching ...');
      state.searchText = this.searchText;
      console.log(state.searchText);
    },
  },
}
</script>

<style lang="scss">

@use '@/assets/scss/style.scss';
@import '@/assets/scss/variables.scss';


.header{
  background-color: $header-bg;
  img{
    height: 60px;
  
  };
  .button{
    border: 1px solid $spotify-primary
  };
  .search{
    height: 50px;
    z-index: 3;
  }
}
</style>
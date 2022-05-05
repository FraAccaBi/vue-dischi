<template>
  <div class="header" >
    <img class="d-flex justify-content-start" src="../../public/Spotify_App_Logo.png" alt="">
    
  </div>
</template>

<script>


export default {
  name: 'SiteHeader',
  components: {
    
  }
}
</script>

<style lang="scss">

@use '@/assets/scss/style.scss';


.header{
  background-color: #2E3A46;
  img{
    height: 60px;
  
  }
}
</style>
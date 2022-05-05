<template>
  <div >
     <div class="col" >
        <img :src="poster" alt="title" />
        <div>{{title}}</div>
        <div>{{author}}</div>
        <div>{{year}}</div>
    </div>
  </div>

    
  
</template>

<script>

export default {
  name: 'DiskComponent',
  props: {
    poster: URL,
    title: String,
    author: String,
    year: String
  }
}
</script>

<style lang="scss">

</style>
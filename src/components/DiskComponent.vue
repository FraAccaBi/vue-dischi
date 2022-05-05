<template>
  <div >
     <div class="col" >
        <img :src="album.poster" alt="" />
        <h2>{{ album.title }}</h2>
        <div>{{ album.author }}</div>
        <div>{{ album.year }}</div>
    </div>
  </div>

    
  
</template>

<script>

export default {
  name: 'DiskComponent',
  props: {
    album: Object
  }
}
</script>

<style lang="scss">

</style>
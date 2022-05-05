<template>
  <div >
     <div class="col card" >
        <img :src="poster" alt="title" />
        <div class="title">{{title}}</div>
        <div class="text">
          <div>{{author}}</div>
          <div>{{year}}</div>
        </div>
        
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

<style lang="scss" scoped>
img{
  height: 160px;
}
.card{
  background-color: #2E3A46 ;
  height: 280px;
  padding: 1rem;
}
.text{
  color: #6D6660;
}
.title{
  color: #ffffff;
  text-transform: uppercase;
  font-weight: 600;
  font-size: larger;
  
}
</style>
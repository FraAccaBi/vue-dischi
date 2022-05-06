<template>
  <div class="d-flex justify-content-end pe-4">
  <form class="d-flex" @submit.prevent="$emit('formSubmit')">
      <input
        class="form-control me-2"
        type="search"
        placeholder="Search author"
        aria-label="Search"
        :value="searchText"
        @input="$emit('input', $event.target.value)"
        @keyup="$emit('formSubmit', searchText)"

      />
      <button
        class="btn btn-outline-success d-flex align-items-center"
        type="submit"
        :disabled="searchText < 1"
      >
        <font-awesome-icon icon="fa-solid fa-magnifying-glass" />
        Search
      </button>
      <div class="dropdown">
  <button class="btn dropdown-toggle" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
    What's your mood today?
  </button>
  <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
    <li><a class="dropdown-item" href="#">Rock</a></li>
    <li><a class="dropdown-item" href="#">Pop</a></li>
    <li><a class="dropdown-item" href="#">Jazz</a></li>
    <li><a class="dropdown-item" href="#">Metal</a></li>
  </ul>
</div>
    </form>
  </div>
 
</template>

<script>
export default {
    name:"SearchBox",
    props: {
        searchText: String,
    }
};
</script>

<style lang="scss">

@import '@/assets/scss/variables.scss';
.form-control{
  width: 150px;
}


</style>
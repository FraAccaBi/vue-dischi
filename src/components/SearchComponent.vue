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
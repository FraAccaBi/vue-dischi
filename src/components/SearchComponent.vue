<template>
  <form class="d-flex" @submit.prevent="$emit('formSubmit')">
    <input
      class="form-control me-2"
      type="search"
      placeholder="Search"
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
</template>

<script>
export default {
    name:"SearchBox",
    props: {
        searchText: String,
    }
};
</script>

<style>
</style>
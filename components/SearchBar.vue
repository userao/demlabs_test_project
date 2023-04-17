<template>
  <div class="search-bar">
    <div class="search-bar__input-group flex">
      <img src="~/assets/images/search.png" />
      <input type="text" placeholder="Search" class="search-bar__input" />
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({}),
}
</script>

<style scoped>
.search-bar {
  grid-column-start: 2;
  grid-column-end: 4;
  padding: 1rem 0 1rem 2.25rem;
  border: solid 1px #49455a;
  border-right: none;
  border-bottom: none;
  border-radius: 0px 0px 0px 16px;
  height: fit-content;
  box-shadow: 5px 5px 10px rgba(8, 7, 13, 0.42), inset 1px 1px 0px #524d64;
}
.search-bar__input-group {
  width: 14rem;
  padding-bottom: 0.375rem;
  gap: 1rem;
  border-bottom: solid 1px #393b41;
}

.search-bar__input {
  color: #fff;
  flex-grow: 1;
  background: none;
  border: none;
}

.search-bar__input:focus {
  outline: none;
}
</style>
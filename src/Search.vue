<template>
<div class="search">
  <mdb-input label="Search" type="text" class="mt-0"/>
</div>
</template>

<script>
  import { mdbInput } from 'mdbvue';

  export default {
    name:'SearchBar',
    components: {
      mdbInput
    }
  }
</script>
<style scoped>
.search {
    width: 50%;
    margin: auto;
    padding: 10px;
}
</style>
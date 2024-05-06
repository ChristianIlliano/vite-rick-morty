<script>
import axios from "axios";

export default {
  components: {
    AppHeader,
    AppMain,
  }
data() {
  return {
    charArray: []
  };
},
created() {
  axios.get("https://rickandmortyapi.com/api/character", {
    params: {

    }
  })
  .then((resp) => {
    this.charArray = resp.data.data;
  })
}
}
</script>

<template>
<AppHeader />
<AppMain />

</template>

<style lang="scss" scoped>

</style>
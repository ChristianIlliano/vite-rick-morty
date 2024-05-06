<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppChar from "./components/AppChar.vue";

export default {
  components: {
    AppHeader,
    AppMain,
    AppChar,
  },
  data() {
    return {
      charArray: [],
  };
},
created() {
  axios
    .get("https://rickandmortyapi.com/api/character", {
      params: {
        id: 20,
        offset:0,
    },
  })
  .then((resp) => {
    this.charArray = resp.data.results;
    console.log(this.charArray, resp);
  });
},
};
</script>

<template>
<AppHeader />
<AppMain :charArray="charArray"/>

</template>

<style lang="scss" scoped>

</style>
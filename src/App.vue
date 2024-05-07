<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppChar from "./components/AppChar.vue";
import AppSearch from "./components/AppSearch.vue";

export default {
  components: {
    AppHeader,
    AppMain,
    AppChar,
    AppSearch,
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
          id: 21,
          offset: 0,
        },
      })
      .then((resp) => {
        this.charArray = resp.data.results;
        console.log(this.charArray);
      });
  },

  methods: {
    getStatus() {
      console.log("stoCambinado");
      // Costuriamo i parametri per la chiamata axios
      //   const paramsObj = {
      // }
    }
  },

};
</script>

<template>
  <AppHeader />
  <AppSearch @filter="getStatus()" />
  <AppMain :charArray="charArray" />

</template>

<style lang="scss" scoped></style>
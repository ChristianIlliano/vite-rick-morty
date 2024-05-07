<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppChar from "./components/AppChar.vue";
import AppSearch from "./components/AppSearch.vue";
import {store} from "./store";

export default {
  components: {
    AppHeader,
    AppMain,
    AppChar,
    AppSearch,
  },
  data() {
    return {
      store,
      charArray: [],
    };
  },
  created() {

  },

  methods: {
    getStatus() {

      const paramsObj = {
        num: 20,
      };

      if (this.store.selectedStatus !== "All") {
        paramsObj.status = this.store.selectedStatus;
      }

      console.log("stoCambinado", this.store.selectedStatus);

     axios.get("https://rickandmortyapi.com/api/character", {
      params: paramsObj,

     }).then((resp) => {
      this.charArray = resp.data.results;
      this.store.charList = resp.data.results
     });
      // Costuriamo i parametri per la chiamata axios
      //   const paramsObj = {
      // }

    }
  },

};
</script>

<template>
  <AppHeader />
  <AppSearch @filter="getStatus" />
  <AppMain :charArray="charArray" />

</template>

<style lang="scss" scoped></style>
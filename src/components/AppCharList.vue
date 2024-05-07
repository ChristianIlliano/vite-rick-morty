<script>
import { store } from "../store";
import AppCard from "./AppChar.vue";

export default {
  components: {
    AppChar,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="container">
    <div class="row row-cols-4">
      <div class="col" v-for="card in store.charList">
        <AppChar :cardObj="card" />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
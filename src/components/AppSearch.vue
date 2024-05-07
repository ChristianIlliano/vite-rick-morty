<script>
import {store} from "../store"
export default {
data() {
    return {
        store,
        status: ["Alive", "unknown", "Dead"]
    }
},

methods:{

},
};
</script>

<template>
 <div class="container py-4">
    <div class="d-flex justify-content-between">
      <div>
        <select @change="$emit('filter')" v-model="store.selectedStatus">
          <option :value="statusAtm" v-for="statusAtm in status">
            {{ statusAtm }}
          </option>
        </select>
      </div>
      <!-- <p>Mostrati {{ store.cardsList.length }} elementi</p> -->
    </div>
  </div>
</template>

<style>

</style>
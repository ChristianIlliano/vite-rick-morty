<script>
import AppChar from "./AppChar.vue";
export default {
    components: {
        AppChar,
    },
    props: {
        charArray: Array,
    },
};
</script>

<template>
    <div class="container">
        <div class="row row-cols-1 row-cols-md-3 row-cols-lg-4">
            <div class="col" v-for="char in charArray" v-if="charArray.length">
                <AppChar :charObj="char"/>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>

</style>
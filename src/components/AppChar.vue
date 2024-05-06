<script>
export default {
    props: {
        charObj: Object,
    },
};
// speciesCheck() {
//     if charObj.status === "human" {
        
//     }
// }
</script>

<template>
<div class="char m-2 p-2">

<img class="img-circle" :src="charObj.image" alt="">
<h5>{{ charObj.name }}</h5>
<p>{{ charObj.status }} <br> {{ charObj.species }}</p>
</div>
</template>

<style lang="scss" scoped>
.char {
    color: white;
    border-radius: 20px;
    background-color: #40b5cb;
    border: 6px solid #c0df40;
    text-align: center;
    h5 {
        padding-top: 10px;
        font-size: 1.4rem;
        font-family: Arial, Helvetica, sans-serif;
        font-weight: bold;
    }

    .img-circle {
        border-radius: 50%;
        border: 6px solid #c0df40;
    }
};
</style>
<template>
    <div class="top" >
         <div class="top_logo"></div>

    </div>

</template>

<script>
    export default {
        name: "top"
    }
</script>

<style scoped>
    .top {
        background: url(../assets/imgs/h_top.png) no-repeat center center;
        height: 216px;
        width: 100%;

    }

    .top_logo {
        margin: 0 auto;
        width: 1200px;
        height: 216px;
        background: url(../assets/imgs/h_top_logo.png) no-repeat;
        z-index: 9;
    }
</style>
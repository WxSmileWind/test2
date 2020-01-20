<template>
    <div>
        sdfdsada

    </div>
</template>

<script>
    export default {
        name: "read",
        created() {
            console.log('-------------------------id',this.$route.params.id);
            //this.name = this.$route.params.id;
            document.getElementById("public_title").innerHTML='新闻-'+this.$route.params.id
        },
    }
</script>

<style scoped>

</style>
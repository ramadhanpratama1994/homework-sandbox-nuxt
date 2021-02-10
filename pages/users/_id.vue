<template>
    <div>
        <h1>{{name + " " + this.$route.params.id}}</h1>
    </div>
</template>

<script>
export default {
    asyncData({}) {
        console.log("ini async data");
        return {
            name: "Ramadhan Pratama"
        };
    },
    created() {
        console.log("ini created");
    },
    mounted() {
        console.log("ini mounted")
    },
}
</script>
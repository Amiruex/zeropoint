<template>
    <button @click="count++">点击了{{count}}次</button>
</template>

<script>
    export default {
        name: "Index",
        data:function () {
            return {
                count:0
            }
        }
    }
</script>

<style scoped>
    button {
        color: red;
    }
</style>
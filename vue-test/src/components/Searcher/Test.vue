<template>
    <div>
        <searcher v-model="searcherTxt"
                  @start-search="startSearch"></searcher>
        {{searcherTxt}}
    </div>
</template>

<script>
    import Searcher from './Searcher'
    export default {
        name: "Test",
        components:{
            Searcher
        },
        data:function () {
            return {
                searcherTxt:"xxx"
            }
        },
        methods:{
            startSearch:function (txt) {
                console.log('开始搜索: '+txt);
            }
        }
    }
</script>

<style scoped>

</style>
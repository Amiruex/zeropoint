<template>
    <div>
        <div>
        <span v-for="(s,i) in stars" :key='i' :class="s"></span>
        </div>
        <!-- <input type="number" min="0" max="5" step="0.5" value="0.5" v-model="score"> -->
        <input type="number" min="0" max="5" step="0.5" v-model="score">
    </div>
</template>
<script>
export default {
    name:'Star',
    data(){
        return{
          score:3
        //    stars:['on','on','on','half','off']
        }
    },
    computed:{
        stars(){
            var s=[];
            for(let i =1;i<=this.score;i++){
                s.push('on');
            }
            if(this.score-s.length>0){
                s.push('half');
            }
            while(s.length<5){
                s.push('off');
            }
            return s;
        }
    },
     props:{
        // score:{
        //     type:Number,
        //     require:true
        // }
    }
}
</script>
<style scoped>
.on{
    display: inline-block;
    width: 60px;
    height: 60px;
    background: url("./img/star48_on.png") no-repeat;
}
.half{
    display: inline-block;
    width: 60px;
    height: 60px;
    background: url("./img/star48_half.png") no-repeat;
}
.off{
    display: inline-block;
    width: 60px;
    height: 60px;
    background: url("./img/star48_off.png") no-repeat;
}
</style>
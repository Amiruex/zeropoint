<template>
    <div>
         <ul>
            <li @click="cname='Pop',change(1)" :class="{ active:cname=='Pop'}">弹出框</li>
            <li @click="cname='Star',change(2)" :class="{ active:cname=='Star'}">评星级</li>
            <li @click="cname='Note',change(3)" :class="{ active:cname=='Note'}">记事本</li>
            <div class="line" :style="{left:lineX+'px',transition:'all ease-in-out .3s'}"></div>
        </ul>

        <transition-group tag="div" class="wrap">
            <component :is='cname' :key='cname'></component>
        </transition-group>
    </div>
</template>
<script>
import Pop from '../../components/PopConfirm/pop.vue'
import Star from '../../components/Star/star.vue'
import Note from '../../components/Note/note.vue'

export default {
    name:'DTab',
    components:{
        Pop,
        Star,
        Note
    },
    data(){
        return{
             cname:'Pop',
             lineX: 0,
        }
    },
    methods: {
        change(index) {
            if (index == 1) {
                this.lineX = 0;
            } else if (index == 2) {
                this.lineX = 82;
            } else {
                this.lineX = 164;
            }
            // console.log(e);
        }
    },
}
</script>
<style lang="css" scoped>
 ul {
    list-style: none;
    position: relative;
    padding: 0;
    overflow: hidden;
    margin: 0;
}

ul li {
    float: left;
    width: 80px;
    height: 30px;
    line-height: 30px;
    text-align: center;
    /* color: aquamarine; */
    background-color: #bfa;
    border-radius: 10px 10px 0 0;
    border: 1px solid green;
}

.active {
    background-color: cornflowerblue;
    /* border-bottom: 2px solid #ff8888; */
}

.line {
    width: 78px;
    border: 2px solid #ff8888;
    position: absolute;
    top: 28px;
}

.content {
    width: 360px;
    height: 400px;
    position: absolute;
}

.d1 {
    background-color: lightskyblue;
}

.d2 {
    background-color: mediumseagreen;
}

.d3 {
    background-color: plum;
}

.wrap {
    width: 360px;
    position: relative;
}

.v-enter {
    opacity: 0;
    left: 60px;
}

/* .v-leave-to {
    opacity: 0;
} */
/* 动画结束 */

.v-enter-to {
    opacity: 1;
    left: 0;
}

/* .v-leave {
    opacity: 1;
} */

.v-enter-active{
    transition: all 1s;
}
</style>
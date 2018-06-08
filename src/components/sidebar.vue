<template>
    <div class="sidebar">
        <div class="container">
            <div v-bind:class="{active1: activate === 0}"><svg class="icon" aria-hidden="true" v-on:mouseenter="activate = 0" v-bind:class="{active: activate === 0}">
            <use xlink:href="#icon-gerenzhongxin"></use></svg></div>
            <div v-bind:class="{active1: activate === 1}"><svg class="icon" aria-hidden="true" v-on:mouseenter="activate = 1" v-bind:class="{active: activate === 1}">
            <use xlink:href="#icon-jiaoyubeijing" ></use></svg></div>
            <div v-bind:class="{active1: activate === 2}"><svg class="icon" aria-hidden="true" v-on:mouseenter="activate = 2" v-bind:class="{active: activate === 2}">
            <use xlink:href="#icon-10" ></use></svg></div>
            <div v-bind:class="{active1: activate === 3}"><svg class="icon" aria-hidden="true" v-on:mouseenter="activate = 3" v-bind:class="{active: activate === 3}">
            <use xlink:href="#icon-zhuanyejineng" ></use></svg></div>
        </div>
        <!-- <ul>
            <li v-for="(item, index) in things" :key='item.id'>
                <edit v-bind:title="item" v-bind:class="{active2: activate === index}"  v-bind:addOne="addOne"/>
            </li>
        </ul> -->
        <div v-for='(value,key,index) in content' v-bind:key="key.id" class="list">
        <edit v-bind:titles="key" v-bind:class="{active2: activate === index}" /></div>
          <preview class="preview" />
    </div>
           
</template>

<script>
import edit from "./edit.vue"
import preview from './preview.vue'
import { mapState } from 'vuex'
export default {
    name: 'sidebar',
    data: function(){
            return{
                activate:0,
            }
    },
    computed:{
  ...mapState({
    content: state => state.resume,
  })
},
    methods:{
      
    },
    components:{edit,preview}
}
</script>

<style lang="scss" scoped>
.icon {
       width: 40px; height: 40px;
       vertical-align: -0.15em;
       fill: lightcoral;
       overflow: hidden;
       margin: 20px 0;
    }
.active {
    transform: scale(1.5);
    transition: all 0.3s;
}
.active1{
    opacity: 0.5;;   
     box-shadow: -1px 1px 10px -1px rgba(0,0,0,0.5); 
    transition: all 0.3s;
    border-radius: 5px;
}
.active2 {
    display: block;
}
.sidebar{
    display: flex;
    .container{
            display: flex;
            flex-direction: column; 
            justify-content: flex-start;
            align-items: center;
            background-color: lightblue;
            width: 120px;
            div {
                padding: 0 40px;
            } 
            }
    .list {
        overflow: auto;
    }
    .preview {
        flex-grow: 1;
    }
   
} 
</style>


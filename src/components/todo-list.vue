<template>
    <div>
        <input type="text" v-model="content" v-on:keyup.enter="add">
        <li v-for='(item, index) in data1' v-bind:key="item.id">
            {{index+'.'}}<input type="checkbox" v-model="data1[index].down" true-value="已完成"
  false-value="未完成"/>{{item.nr}}{{data1[index].down}}
            <button v-on:click="del(index)">X</button>
        </li>
    </div>
</template>

<script>
export default {
    data:function(){
        return {data1:[],
            content:'',
            // num:{},
    }},
    // computed:{
    //     isdown:function(){
    //         for(var i = 0; i < this.data1.length; i++){
    //        console.log(this.data1.length)
    //         if (this.data1[i].down === true){
    //             this.num[i]='已完成'
               
    //         } else {
    //             this.num[i]='未完成'
    //         }}
    //         console.log(this.num)
    //         return this.num
    //          }
    //     },
    methods:{
        add: function(){
            let data2 = {nr:this.content,down:'未完成'}
           
            this.data1.push(data2)
        },
        del:function(n){
            this.data1.splice(n,1)
        }
    }
}
</script>

//或者用v-if，也能实现相同的效果，同样很优雅。。。
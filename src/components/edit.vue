
<template>
<div class="input-content">
    <div v-for='(item, index) in contents' v-bind:key='item.id'>
    <div v-for='(value, key) in item' v-bind:key='key.id'>
    <label>{{key}}</label>
    <el-input  placeholder="请输入内容" v-bind:value="value" v-on:input="update(key,index)"></el-input>
   </div>
    <el-row class="submit-button">  
      <el-button type="primary" plain v-on:click='addOne'>增加一项</el-button>
      <el-button type="primary" plain v-on:click='deleteOne(index)'>删除此项</el-button>
    </el-row>
    </div>
</div>
</template>

<script>
import { mapState } from 'vuex'
export default {
 
computed:
 mapState({
    contents(state){
      return state.resume[this.titles]
    },
  }),
methods:{
  update:function(n,index){
     let obj = {
        t:this.titles,
        title: n,
        ind: index,
        value: event.target.value
      }
      console.log(obj)
    this.$store.commit('updateData', obj)
  },
  addOne:function(){
    this.$store.commit('updateList',this.titles)
  },
  deleteOne:function(n){
    if(this.contents.length > 1){
      let obj = {
        title: this.titles,
        index: n
      }
       this.$store.commit('deleteList',obj)
    }  
  }},
  props:['titles']
}
</script>

<style lang="scss" scoped>
.input-content{
    max-width:320px;
    margin: 20px;
    display: none;
    list-style: none;
    div{
      overflow: auto;
      label {
        padding:8px 0;
        display: inline-block;
      }
      .submit-button{
        margin: 10px 0;
      } 
    }
}
</style>

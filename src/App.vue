<template>
  <div id="container">
    <div v-if='getPath === "/signUp"'>
      <signUp/>
    </div>
    <div v-else-if='getPath === "/logIn"'>
      <logIn/>
    </div>
    <div v-else>
      <topbar id="topbar"/>  
      <sidebar id="main"/>  
    </div>
  </div>
</template>

<script>
import topbar from './components/topbar.vue'
import sidebar from './components/sidebar.vue'
import signUp from './components/signUp.vue'
import logIn from './components/logIn.vue'

export default {
  name: 'app',
  created(){
    let s = window.location.pathname
    window.history.replaceState({state:s},null,s)
    this.$store.commit('setPath',s)
  },
  mounted(){
    let that = this
    window.onpopstate = function(){
      let s = window.history.state.state
          that.$store.commit('setPath',s)
    }
  },
  computed:{
    getPath(){
      return this.$store.state.path
    }
  },
  components:{topbar,sidebar,signUp,logIn}
}
</script>

<style lang="scss">
html, body, #container {
  height: 100%;
  margin: 0;
  flex-direction: column;
}
#container{
  display: flex;
  #main{
    flex-grow: 1;
  }
}
</style>

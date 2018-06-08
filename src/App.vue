<template>
  <div id="container">
    <topbar id="topbar"/>  
    <sidebar id="main"/>
  
  </div>
</template>

<script>
import topbar from './components/topbar.vue'
import sidebar from './components/sidebar.vue'

export default {
  name: 'app',
  components:{topbar,sidebar,}
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

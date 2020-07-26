<template>
  <div>
    <navbar />
    <sidebar />
    
    <div class="content">
      <Content />
    
      
    </div>

    
  </div>
  
</template>

<script>
import Navbar from './components/Navbar.vue'
import Sidebar from './components/Sidebar.vue'
import Content from './components/Content.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Sidebar,
    Content,
  }
}
</script>

<style scoped>
.content {
  font-family: Open sans, Avenir, Helvetica, Arial, sans-serif;
  color: #707070C4;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding-top: 100px;
  background-color: #F7F7F7; 
}

</style>

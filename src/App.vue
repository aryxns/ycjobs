<template>
  <div id="app">
    <jobs></jobs>
    <div class="footer">
      <div class="footer_contents"></div> 
    </div>      
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Jobs from './components/Jobs.vue'

export default {
  name: 'App',
  components: {
    'jobs': Jobs,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.footer {
  height:24px; 
  width: 100%; 
  background-image: none;
  background-repeat: repeat;
  background-attachment: scroll;
  background-position: 0% 0%;
  position: fixed;
  bottom: 0pt;
  left: 0pt;
} 

.footer_contents {
  height:24px; 
  width: 1000px; 
  margin:auto;
}
</style>
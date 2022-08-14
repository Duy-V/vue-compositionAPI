<template>

<div>
  <div>The name of the channel is {{userName}}</div>
</div>

  <nav>
    <router-link to="/">Home</router-link> |
    
  </nav>
  <router-view/>
</template>
<script>
import {ref} from 'vue';
export default {
 name:"App",
 setup() {
let name = ref('Leela Web Dev');
setTimeout(() => {
  console.log('executing time out in setup');
  console.log(name)
  name.value='Leela';
}, 3000)
return {
  userName: name.value,

}
 },
 data() {

 },
 mounted() {
setTimeout(() => {
this.userName = 'Leela'
}, 3000)
 },
 computed: {
  

 },
 methods: {
  
  

 },
 components: {
  
 }
}
</script>
>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>

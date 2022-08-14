<template>

<div>
  <div>The name of the channel is {{userName}}</div>
  <h3>UserDetails</h3>
  <div>Name: {{userDetails.name}}</div>
  <div>Age: {{userDetails.age}} </div>
</div>

  <nav>
    <router-link to="/">Home</router-link> |
    
  </nav>
  <router-view/>
</template>
<script>
import {ref, reactive, isRef, isReactive,} from 'vue';
export default {
 name:"App",
 setup() {
let name = ref('Leela Web Dev');
let userDetails = reactive({
  name:'Leela',
  age: 30,
});
console.log(name.value);
console.log(userDetails.name);
console.log(isRef(name));
console.log(isReactive(userDetails));
console.log(isRef(name.value));
console.log(isReactive(userDetails.name));
setTimeout(() => {
  console.log('executing time out in setup');
  console.log(name);
  name.value='Leela';
  userDetails.name = 'Modified Leela';
  userDetails.age = 30;
}, 3000)
return {
  userName: name,
  
  userDetails: userDetails,

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

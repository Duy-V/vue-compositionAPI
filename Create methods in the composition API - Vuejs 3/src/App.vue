<template>

<div>
  <div>{{userName}}</div>
  <div>
    <input type="text" placeholder="First Name" />&nbsp;
    <!-- <input type="text" placeholder="First Name" @input="changeFirstName()"/>&nbsp; -->
    <input type="text" placeholder="Last Name" />
    <!-- <input type="text" placeholder="Last Name" @input="changeLastName()"/> -->
  </div>
  <h3>UserDetails</h3>
  <div>Name: {{userDetails.name}}</div>
  <div>Age: {{userDetails.age}} </div>
  <button @click.prevent= 'changeName'>Change Name</button>
</div>

  <nav>
    <router-link to="/">Home</router-link> |
    
  </nav>
  <router-view/>
</template>
<script>
import {ref, reactive} from 'vue';
export default {
 name:"App",
 setup() {
let name = ref('Leela Web Dev');

let userDetails = reactive({
  name:'Leela',
  age: 30,
});


// function changeFirstName(event) {
//   firstName = event.target.value;
// }
// function changeLastName(event) {
//   lastName = event.target.value;
// }

function changeName() {
  userDetails.name = 'Modified Leela'
}

return {
  userName: name,
  
 userDetails,
changeName,
// changeFirstName,
// changeLastName,
// fullName,
}
 },
//  data() {

//  },
//  mounted() {
// setTimeout(() => {
// this.userName = 'Leela'
// }, 3000)
//  },
//  computed: {
  

//  },
//  methods: {
  
  

//  },
//  components: {
  
//  }
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

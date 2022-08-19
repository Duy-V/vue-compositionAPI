<template>

<div>
  <h1>{{fullName}}</h1>
  <h1>{{age}}</h1>
  <button @click="updateAge">Update Age</button>
  <div>
    
    <input type="text" placeholder="First Name" @input="changeFirstName" v-model="firstName"/>&nbsp;
    
    <input type="text" placeholder="Last Name" @input="changeLastName" v-model="lastName"/>&nbsp;
  </div>
  
  <!-- <h3>UserDetails</h3>
  <div>Name: {{userDetails.name}}</div>
  <div>Age: {{userDetails.age}} </div>
  <button @click.prevent= 'changeName'>Change Name</button> -->
 
</div>

  <nav>
    <router-link to="/">Home</router-link> |
    
  </nav>
  <router-view/>
   <UserData :user-details="userDetails" class="leelaclass" @changeFirstName='firstNameChange'>
    <template>
      <div>Header Slot</div>
    </template>
    <div>Hai Slot Leela</div>
    </UserData>
</template>
<script>
import {ref, reactive, computed,watch} from 'vue';
import UserData from "./components/UserData.vue"
export default {
  components: {
    UserData
  },
 name:"App",
 setup() {
let name = ref('Leela Web Dev');
let age = ref(30);
let firstName = ref('');
let lastName = ref('');

let userDetails = reactive({
  name:'Leela',
  age: 30,
});
const fullName = computed(() => {
  return firstName.value + ' ' + lastName.value
});
watch([age,fullName], (newValue, oldValue) => {
console.log(newValue)
console.log(oldValue)
})

function updateAge () {
  age.value = 100;
}
function changeName() {
  userDetails.name = 'Modified Leela'
}
function firstNameChange(event) {
  firstName.value = event;
}
return {
  userName: name,
  
 userDetails,
changeName,
firstName,
lastName,
fullName,
age,
updateAge,
firstNameChange,
}
 },

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

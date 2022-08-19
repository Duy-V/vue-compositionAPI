<template>
    <div>
        <h3>UserDetails</h3>
  <div>Name: {{user.name}}</div>
  <div>Age: {{user.age}} </div>
  <slot>name="header"</slot>
  <div>{{fullDetails}}</div>
  <button @click.prevent= 'changeName'>Change Name</button>
  <div>
    <input type="text" ref="ageref"/>
    <button @click.prevent="changeAge()">Change Age</button>
  </div>
  <div>
    <button @click.prevent="changeFirstName">Change FirstName</button>
  </div>
  <slot></slot>
    </div>
</template>
<script>
import {reactive,computed,ref} from "vue";

export default {
  name:"UserData",
  props: {
    userDetails: {
        required: true,
    }
  } , 
  setup(props,context){
    console.log(context.attrs);
    const ageref = ref(null);
    const user = reactive(props.userDetails);


    const fullDetails = computed(() => {
        return user.name + 'age: ' + user.age;
    })
function changeName() {
    props.userDetails.name ="Modifile Leela"
} 
function changeAge() {
    user.age = ageref.value.value
}
function changeFirstName() {
context.emit('change-first-name','emitted changes Name')
}
return {
    changeName,
    user,
    fullDetails,
    ageref,
    changeAge,
    changeFirstName,
}

}
}
</script>

<template>
  <div>Life Cycle Hooks</div>  
  <div>{{state.name}}</div>
  <div><button @click.prevent="state.name='Updated leela web dev'">
    Update Name</button></div>
</template>
<script>
import {onBeforeMount, onMounted,onBeforeUpdate,onBeforeUnmount,onRenderTracked,onUpdated,onRenderTriggered, onUnmounted, reactive} from 'vue';

export default {
    name: 'LifeCycle',
   
   setup() {
 const state = reactive({
 name:'Leela web dev',

 })

    onBeforeMount(() => {
        console.log('before Mounted')
    });
    onMounted(() => {
        console.log('on Mounted')
    });
    onBeforeUpdate(() => {
        console.log('on before updated')
    });
    onUpdated(() => {
        console.log('on updated')
    });
    onBeforeUnmount(() => {
        console.log('on before unmount')
    });
    onUnmounted(() => {
        console.log('on unmounted')
    });
    onRenderTracked((e) => {
        console.log(e)
    });
    onRenderTriggered((e) =>{
        console.log(e)
    })
    return {state }
   } 
}
</script>

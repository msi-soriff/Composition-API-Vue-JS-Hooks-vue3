<template>
  <h2>{{ state.count }}, doubled = {{ state.double }}</h2>
  <button @click="UpdateCount(true)">Increase</button>
  <button @click="UpdateCount(false)">Decrease</button>
</template>

<script>
// import { ref } from 'vue';
import { reactive, computed } from 'vue';

export default {
  setup(){
    const state = reactive({
      count: 0,
      double: computed (()=> state.count * 2)
    });
    
    // function increment(){
    //   count.value++;
    // }

    function UpdateCount (increase){
      if (increase)
        state.count++;
      else
        state.count--
    }

    // function decrease (){
    //   count.value--;
    // }

    return{
      state,
      UpdateCount
      // increment,
      // decrease 
    }
  }
}
</script>


<style scoped>
*{
  font-family: 'Courier New', Courier, monospace;
  font-size: 2rem;
}
  button{
    color: rgb(184, 207, 207);
    padding: 10px;
    border: 2px solid;
  }
</style>

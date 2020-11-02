<template>
  <div style='border: 1px solid blue;'>
    <LifeCycle v-if="type" />
    <Hello :msg="message"/>
    <button @click="type =!type">Destroy</button>
    <Input/>
  </div>
</template>

<script>
import LifeCycle from "@/components/LifeCycle";
import Hello from "@/components/HelloWorld";
import Input from '@/components/Input';

export default {
  name: "App",
  components: {
    Input,
    LifeCycle,
    Hello
  },
  data: function(){
    return {
      type: true,
      message: 'dari komponent'
    }
  }
};
</script>

<style>
</style>

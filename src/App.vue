<template>
  <div style="border: 1px solid blue">
    <!-- <LifeCycle v-if="type" /> -->
    <Hello :msg="message" />
    <button @click="type = !type">Destroy</button>
    <Input />
    <div>
      <h2 v-if="greeting !== 'selamat sore'">HALO</h2>
      <h2 v-else-if="!greeting">Selamat pagi</h2>
      <h2 v-else-if="!greet">Selamat malam</h2>
      <h2 v-else>Selamat sore</h2>

      <div>
        <h3 v-show="!greeting">Selamat Siang</h3>
      </div>
    </div>
  </div>
</template>

<script>
// import LifeCycle from "@/components/LifeCycle";
import Hello from "@/components/HelloWorld";
import Input from "@/components/Input";

export default {
  name: "App",
  components: {
    Input,
    // LifeCycle,
    Hello,
  },
  data: function () {
    return {
      type: true,
      message: "dari komponent",
      greeting: "selamat sore",
      greet: "selamat malam",
    };
  },
};
</script>

<style>
</style>

<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <GreetnigComp msg="Welcome to Quiz App" />
  </div>
</template>

<script>
// @ is an alias to /src
import GreetnigComp from "@/components/GreetnigComp.vue";

export default {
  name: "HomeView",
  components: {
    GreetnigComp,
  },
};
</script>

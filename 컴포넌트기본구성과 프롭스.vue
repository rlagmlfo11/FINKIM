<template>
  <GreetingUser :username="username"></GreetingUser>
  <GreetingUser username="awesome"></GreetingUser>
  <GreetingUser username="FINKIM"></GreetingUser>
  <GreetingUser username="geeks"></GreetingUser>
  <GreetingUser></GreetingUser>

  <button @click="changename">change</button>
</template>

<script>
import GreetingUser from "./components/GreetingUser.vue";

export default {
  components: { GreetingUser },
  data() {
    return {
      username: "KIMHEERAE",
    };
  },
  methods: {
    changename() {
      this.username = "DDOCHI";
    },
  },
};
</script>

<style></style>
-->

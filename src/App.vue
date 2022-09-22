<template>
  <div class="">
    <Form />
    <TimeLine />
    <Resources />
  </div>
</template>

<script>
import Form from "./components/Form.vue";
import Resources from "./components/Resources.vue";
import TimeLine from "./components/TimeLine.vue";

export default {
  name: "App",
  components: { Form, Resources, TimeLine },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

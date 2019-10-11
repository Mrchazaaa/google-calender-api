<template>
  <div id="app" class = "text-center">
    <button class="btn btn-primary">Signin With Google</button>
    <Form class="d-none"/>
  </div>
</template>

<script>
import Form from "./components/Form.vue";
import { handleClientLoad } from "./google-api.js";

export default {
  name: "app",
  components: {
    Form
  },
  mounted: function() {
    handleClientLoad();
  },
};
</script>

<style>
#app {
  padding: 55px;
}
</style>

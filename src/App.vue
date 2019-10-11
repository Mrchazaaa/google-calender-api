<template>
  <div id="app">
    <div class="text-center">
      <button id="authorize_button" class="btn btn-primary" @click="onAuthClick">Signin with Google</button>
      <button id="signout_button" class="btn btn-primary disabled" @click="onSignOutClick">Signout of Google</button>
    </div>
    <Form id="form" class="d-none charliesclass" />
  </div>
</template>

<script>
import Form from "./components/Form.vue";
import { handleClientLoad,
         handleAuthClick,
         handleSignoutClick } from "./google-api.js";

export default {
  name: "app",
  components: {
    Form
  },
  mounted: function() {
    var authorizeButton = document.getElementById('authorize_button');
    var signoutButton = document.getElementById('signout_button');
    var formComponent = document.getElementById('form');

    handleClientLoad(authorizeButton, signoutButton, formComponent);
  },
  methods: {
    onAuthClick: function(event) {
      var myForm = document.getElementById("form");

      handleAuthClick(event);
    },
    onSignOutClick: function(event) {
      handleSignoutClick(event);
    }
  }
};
</script>

<style>
#app {
  padding: 55px;
}
</style>

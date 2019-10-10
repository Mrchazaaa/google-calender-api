<template>
  <div id="app">
    <form @submit.prevent="submitted" id="form-element">
      <h3>Yo checkout my form</h3>
      <div class="form-group">
        <label for="exampleSelect1">Example select</label>
        <select class="form-control" id="exampleSelect1" v-model="selection">
          <option>1</option>
          <option>2</option>
          <option>3</option>
          <option>4</option>
          <option>5</option>
        </select>
      </div>
      <div class="form-group">
        <label for="exampleTextarea">Example textarea</label>
        <textarea class="form-control" id="exampleTextarea" rows="1" v-model="name"></textarea>
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>

    <!-- <ResultsTable :numOfRows="6"/> -->
    <ResultsTable v-bind:numOfRows="this.selection"/>
  </div>
</template>

<script>
import ResultsTable from "./components/ResultsTable.vue";
import {CLIENT_ID, API_KEY} from "./google-api.js";

export default {
  name: "app",
  components: {
    ResultsTable
  },
  formElement: "#form-element",
  data() {
    return {
      selection: "3",
      name: "mr jenkins"
    };
  },
  methods: {
    submitted() {
      
      console.log(this.selection);
      console.log(typeof(this.selection));
      console.log(CLIENT_ID);
      console.log(API_KEY);

    }
  }
};
</script>

<style>
#app {
  padding: 55px;
}
</style>

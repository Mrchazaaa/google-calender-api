<template>
  <div>
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

    <iframe src="https://calendar.google.com/calendar/embed?height=600&amp;wkst=1&amp;bgcolor=%23ffffff&amp;ctz=Europe%2FLondon&amp;src=Y2hhcmxpZS5ob3dsZXR0QGxpdmUuY28udWs&amp;color=%23039BE5&amp;mode=WEEK" style="border-width:0" width="800" height="600" frameborder="0" scrolling="no"></iframe>

    <ResultsTable v-bind:calendarResults="this.calendarResults" />
  </div>
</template>

<script>
import ResultsTable from "./ResultsTable.vue";
import { listUpcomingEvents } from "../google-api.js";

export default {
  name: "Form",
  components: {
    ResultsTable
  },
  formElement: "#form-element",
  data() {
    return {
      selection: "3",
      name: "mr jenkins",
      calendarResults: []
    };
  },
  methods: {
    submitted() {

      var componentScope = this;
      
      listUpcomingEvents().then(function (response) {
        var events = response.result.items;
        componentScope.calendarResults = events;
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
form {
    margin-top: 20px;
}
.table {
  margin-top: 30px;
  border: solid black 2px;
}
thead {
  border-top: none;
  color: white;
}
</style>

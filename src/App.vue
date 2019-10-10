<template>
  <div id="app">
    <form>
      <fieldset>
        <h3>Yo checkout my form</h3>
        <div class="form-group">
          <label for="exampleSelect1">Example select</label>
          <select class="form-control" id="exampleSelect1">
            <option>1</option>
            <option>2</option>
            <option>3</option>
            <option>4</option>
            <option>5</option>
          </select>
        </div>
        <div class="form-group">
          <label for="exampleTextarea">Example textarea</label>
          <textarea class="form-control" id="exampleTextarea" rows="1"></textarea>
        </div>
        <button type="submit" class="btn btn-primary">Submit</button>
      </fieldset>
    </form>

    <!-- <ResultsTable/> -->
  </div>
</template>

<script>
import ResultsTable from './components/ResultsTable.vue'

export default {
  name: 'app',
  components: {
    ResultsTable
  }
}
</script>

<style>
#app {
  padding: 55px;
}
</style>

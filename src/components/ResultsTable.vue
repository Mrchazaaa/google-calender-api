<template>
  <div>
    <table class="table table-striped table-hover">
      <thead>
        <tr class="table-primary">
          <th scope="col">Type</th>
          <th scope="col">Column heading</th>
          <th scope="col">Column heading</th>
          <th scope="col">Column heading</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="entries in Number(numOfRows)" :key="entries.text">
          <th scope="row">Default</th>
          <td>Column content</td>
          <td>Column content</td>
          <td>Column content</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "ResultsTable",
  props: {
    numOfRows: {
      type: String
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.table {
  margin-top: 30px;
  border: solid black 2px;
}
thead {
  border-top: none;
  color: white;
}
</style>

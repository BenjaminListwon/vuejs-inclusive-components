<template>
  <table>
    <caption v-if="caption">{{ caption }}</caption>
    <template v-if="colHeaders">
      <thead>
        <tr>
          <th v-for="header in colHeaders" scope="col">{{ header }}</th>
        </tr>
      </thead>
    </template>
    <tbody>
      <template v-if="rowData && colSpec">
        <tr v-for="(data, rowIndex) in rowData">
          <template v-for="(datum, colIndex) in data">
            <th v-if="colSpec[colIndex].header">{{ datum }}</th>
            <td v-else>{{ datum }}</td>
          </template>
        </tr>
      </template>
      <template v-else-if="rowData">
        <tr v-for="(data, index) in rowData">
          <td v-for="datum in data">{{ datum }}</td>
        </tr>
      </template>
      <template v-else>
        <td>No data available</td>
      </template>
    </tbody>
  </table>
</template>

<script>
export default {
  name: 'VicDatatable',

  props: {
    caption: String,
    colHeaders: Array,
    colSpec: Array,
    rowData: Object,
  },
};
</script>

<style lang="sass" scoped>
table
  width: 100%

  caption
    font-size: 1.25em
    font-weight: 700
    text-align: left

  caption, td, th
    padding: 0.5em 1em

  th
    background: #000
    color: #fff
    text-align: left

  tbody
    tr
      &:hover
        background: #f1f227
        th
          color: #f1f227

</style>
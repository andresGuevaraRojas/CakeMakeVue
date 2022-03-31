<template>
  <table>
    <thead>
      <tr>
        <th v-for="header in headers" :key="header">{{ header }}</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(row, index) in data" :key="index">
        <td v-for="value in row" :key="value">
          <template v-if="Array.isArray(value)">
            <span class="tdManyValues" v-for="m in value" :key="`${m}`">
              {{ m }}
            </span>
          </template>
          <template v-else>
            {{ value }}
          </template>
        </td>
      </tr>
    </tbody>
  </table>
</template>
<script>
export default {
  name: "TableOrders",
  props: {
    headers: Array,
    data: Array,
  },
};
</script>
<style scoped>
table {
  border-collapse: collapse;
}
thead {
  background-color: #8469bf;
}
thead th {
  padding: 1em;
  color: white;
}
tbody {
  border: 1px solid black;
}
tbody td {
  border: 1px solid black;
  padding: 1em;
}
.tdManyValues {
  margin-right: 0.5em;
}
.tdManyValues:last-child {
  margin-right: 0;
}
</style>
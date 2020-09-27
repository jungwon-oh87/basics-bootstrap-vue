<template>
  <b-container>
    <b-row class="row">
      <Card v-for="d in displayData" :key="d.id" :name="d.name" />
    </b-row>
    <b-pagination
      v-model="currentPage"
      :total-rows="rows"
      :per-page="perPage"
      aria-controls="my-table"
      @input="paginate(currentPage)"
    ></b-pagination>
  </b-container>
</template>

<script>
import Card from "@/components/Card";
export default {
  name: "Home",
  data() {
    return {
      myData: [],
      displayData: [],
      currentPage: 1,
      rows: 1,
      perPage: 3,
    };
  },
  components: {
    Card,
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const res = await fetch("data.json");
      const val = await res.json();
      this.myData = val;
      this.displayData = val.slice(0, 3);
      this.rows = this.myData.length;
      // console.log(val);
    },
    paginate(currentPage) {
      const start = (currentPage - 1) * this.perPage;
      this.displayData = this.myData.slice(start, start + 3);
    },
  },
};
</script>

<style scoped>
.temp {
  border: 1px dotted red;
}
.row {
  border: 1px solid blue;
}
</style>

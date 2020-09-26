<template>
  <b-container>
    <b-row class="row">
      <Card v-for="d in myData" :key="d.id" :name="d.name" />
    </b-row>
  </b-container>
</template>

<script>
import Card from "@/components/Card";
export default {
  name: "Home",
  data() {
    return { myData: [] };
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
      // console.log(val);
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

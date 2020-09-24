<template>
  <b-container>
    <b-row class="row">
      <Card />
      <Card />
      <Card />
      <Card />
    </b-row>
  </b-container>
</template>

<script>
import Card from "@/components/Card";
export default {
  name: "Home",
  components: {
    Card,
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

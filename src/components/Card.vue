<template>
  <div>
    <b-col>
      <b-card
        :title="name"
        img-src="https://picsum.photos/600/300/?image=25"
        img-alt="Image"
        img-top
        tag="article"
        style="max-width: 18rem;"
        class="mb-2"
      >
        <b-card-text class="text-left"
          >Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias
          ratione distinctio quod doloremque. Harum ad quos quas, alias
          accusamus sequi.</b-card-text
        >
        <b-button variant="primary">See details</b-button>
      </b-card>
    </b-col>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    name: String,
  },
};
</script>

<style></style>

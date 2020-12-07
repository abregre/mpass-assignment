<template>
  <div>
    <div class="container">
      <SingleTestimonial
        v-for="testimonial of testimonials"
        :key="testimonial.id"
        v-bind:testimonial="testimonial"
        class="card"
      />
    </div>
  </div>
</template>

<script>
import SingleTestimonial from "./SingleTestimonial.vue";

export default {
  name: "Testimonials",
  components: {
    SingleTestimonial,
  },
  props: ["testimonials"],
};
</script>

<style scoped>
.container {
  margin: 4rem 1.6rem;
  display: grid;
  grid-gap: 1.6rem;
  grid-template-columns: 1fr;
  grid-template-rows: auto;
}
.card:nth-child(1) {
  background: hsl(263, 55%, 52%);
  color: hsl(0, 0%, 100%);
}
.card:nth-child(2) {
  background: hsl(217, 19%, 35%);
  color: hsl(0, 0%, 100%);
}
.card:nth-child(3) {
  background: hsl(0, 0%, 100%);
  color: hsl(217, 19%, 35%);
}
.card:nth-child(4) {
  background: hsl(219, 29%, 14%);
  color: hsl(0, 0%, 100%);
}
.card:nth-child(5) {
  background: hsl(0, 0%, 100%);
  color: hsl(217, 19%, 35%);
}

@media only screen and (min-width: 768px) {
  .container {
    width: 100%;
    max-width: 1100px;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
  }
  .card:nth-child(1) {
    grid-column: 1/3;
    grid-row: 1;
  }
  .card:nth-child(2) {
    grid-column: 3/4;
    grid-row: 1;
  }
  .card:nth-child(3) {
    grid-column: 1/2;
    grid-row: 2;
  }
  .card:nth-child(4) {
    grid-column: 2/4;
    grid-row: 2;
  }
  .card:nth-child(5) {
    grid-column: 4;
    grid-row: 1/3;
  }
}
</style>
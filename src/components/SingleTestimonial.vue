<template>
  <div class="card">
    <img
      v-if="testimonial.id == 1"
      src="../../public/assets/quotes.svg"
      class="quotes"
    />
    <div class="card-header">
      <img
        :src="`${testimonial.imageUrl}`"
        alt="userImage"
        class="user-img"
        :class="{ imgBorder: testimonial.id == 1 || testimonial.id == 4 }"       
      />
      <div class="user-info">
        <h4 class="username">{{ testimonial.user }}</h4>
        <h5 class="graduate" v-if="testimonial.verified">Verified Graduate</h5>
      </div>
    </div>

    <div class="card-body">
      <p class="review-title">
        {{ testimonial.reviewTitle }}
      </p>
      <br />
      <p class="review">
        {{ testimonial.review }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingleTestimonial",
  props: ["testimonial"],
};
</script>

<style scoped>
.card {
  position: relative;
  padding: 1.5rem;
  border-radius: 10px;
 -webkit-box-shadow: 12px 11px 41px 9px hsla(0, 0%, 81%, 0.59);
-moz-box-shadow: 12px 11px 41px 9px hsla(0, 0%, 81%, 0.59);
box-shadow: 12px 11px 41px 9px hsla(0, 0%, 81%, 0.59);
}

.card-header {
  display: flex;
  align-items: center;
  margin-bottom: 1rem;
}

.user-img {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin-right: 1rem;
}
.imgBorder {
  border: 3px solid hsl(263, 84%, 63%);
}
.graduate {
  opacity: 0.5;
}
.quotes {
  position: absolute;
  right: 15%;
  top: 0;
  z-index: 0;
}
.review-title {
  position: relative;
  font-size: 20px;
  font-weight: 600;
  z-index: 1;
}
.review {
  font-size: 13px;
  line-height: 18px;
  font-weight: 500;
  opacity: 0.7;
}
</style>
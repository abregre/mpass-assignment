<template>
  <div id="app">
    <Testimonials v-bind:testimonials="testimonials" />
  </div>
</template>

<script>
import axios from "axios";

import Testimonials from "./components/Testimonials.vue";

export default {
  name: "App",
  components: {
    Testimonials
  },
  data() {
    return {
      testimonials: [],
    };
  },
  async created() {
    try {
      const res = await axios.get(`http://localhost:3000/testimonials`);

      this.testimonials = res.data;
    } catch (err) {
      console.error(err);
    }
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Barlow Semi Condensed", sans-serif;
  background: hsl(210, 46%, 95%);
}
#app{
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
@media only screen and (min-width: 768px){
  #app{
    height: 100vh;
  }
}
</style>

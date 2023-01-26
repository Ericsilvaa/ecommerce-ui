<template>
  <div class="container">
    <div class="row">
      <div class="col-12 text-center">
        <h3 class="pt-3">Our Category</h3>
      </div>
    </div>


    <div class="row"></div>
  </div>
</template>

<script>
const axios = require("axios");
// import CategoryBox from "@/components/Category/CategoryBox.vue";
// import axios from 'axios';

export default {
  name: "OurCategory",
  components: {
    // CategoryBox,
  },
  data() {
    return {
      baseURL: "https://limitles-lake-55070.herokuapp.com",
      categories: [],
    };
  },
  methods: {
    async getCategories() {
      await axios
        .get(`${this.baseURL}/category`)
        .then((res) => (this.categories = res.data))
        .catch((err) => console.log(err));
    },
  },
  mounted() {
    this.getCategories();
  },
};
</script>

<style></style>

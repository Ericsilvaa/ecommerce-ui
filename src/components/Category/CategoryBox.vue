<template>
  <div class="card">
    <div>
      <img :src="category.imageUrl" alt="Card image cap" class="card-img-top">
    </div>
    <div class="card-body">
      <h5 class="car-title">{{ category.categoryName }}</h5>
      <p class="card-text">
        {{ category.description  }}
      </p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
  
</template>

<script>
export default {
  name: 'CategoryBox',
  props: ['category'],
  data() {
    return {

    }
  },
  methods: {

  }

}
</script>

<style>

</style>
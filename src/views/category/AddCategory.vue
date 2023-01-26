<template>
    <div class="container">
      <div class="row">
        <div class="col-12 text-center">
          <h3 class="pt-3">Add Category</h3>
        </div>
      </div>

      <div class="row">
        <div class="col-3"></div>

        <div class="col-6">
          <form action="">
          <div class="form-group">
            <label for=""> Name</label>
            <input type="text" class="form-control" v-model="categoryName" name="" id="">
          </div>
          <div class="form-group">
            <label for=""> Description</label>
            <input type="text" class="form-control" v-model="description" name="" id="">
          </div>
          <div class="form-group">
            <label for=""> Image</label>
            <input type="text" class="form-control" v-model="imageURL" name="" id="">
          </div>
          <button type="button" class="btn btn-primary" @click="addCategory"> Submit </button>
          </form>
        </div> 

        <div class="col-3"></div>
        
      </div>

    </div>

</template>

<script>
const axios = require('axios')
const swal = require('sweetalert')


export default {
  data(){
    return {
      categoryName : null,
      description : null,
      imageURL : null,
    }
  },
  methods : {
    async addCategory() {
      const newCategory = {
        categoryName : this.categoryName,
        description : this.description,
        imageUrl : this.imageURL,
      }

      const baseURL = 'https://limitles-lake-55070.herokuapp.com'

      await axios({
        method: 'post',
        url: `${baseURL}/category/create`,
        // this.baseURL+"category/create",
        data : JSON.stringify(newCategory),
        headers: {
          'Content-Type': 'application/json'
        }
      })
      .then(() => {
        //sending the event to parent to handle
        // this.$emit("fetchData");
        // this.$router.push({name:'AdminCategory'});
        swal({
          text: "Category Added Successfully!",
          icon: "success",
          closeOnClickOutside: false,
        });
      })
      .catch(err => console.log(err));
    }
  },
  // mounted(){
  //   if (!localStorage.getItem('token')) {
  //     this.$router.push({name : 'Signin'});
  //   }
  // }
}
</script>

<style>

</style>
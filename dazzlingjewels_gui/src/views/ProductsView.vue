
<template>
  <div class="container">
    <div class="row">
      <h2 class="display-2">Products</h2>
    </div>
    <div class="row justify-content-center gap-3" v-if="Products">
      <div v-for="Product in Products" class="col-2" :key="Product.prodID">
        <div class="col">
          <img :src="Product.image" class="card-img-top img fluid" :alt="Product.prodName" style="height:15rem" />
          <div class="card-body">
            <h5 class="card-title">{{ Product.prodName }}</h5>
            <p class="card-text">Category: {{ Product.category }}</p>
            <h5 class="card-title"> R{{ Product.amount }}</h5>
          </div>
        </div>
      </div>
    </div>
    <div v-else class="row justify-content-center">
      <SpinnerCompVue />
    </div>
  </div>
</template>



<script>
import SpinnerCompVue from '../components/SpinnerComp.vue';

export default {
components: {
  SpinnerCompVue
},
computed: {
  Products() {
    return this.$store.state.Products;
  }
},
mounted() {
  this.$store.dispatch('fetchProducts');
}
};
</script>

styles

<style scoped>

</style>
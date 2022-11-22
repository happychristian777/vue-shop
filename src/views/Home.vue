<template>
<section class="container">

  <range-selector :products="filteredProducts" v-model="max"/>
    <!-- <custom-alert type="danger" close="true" v-if="cartTotal > 100">
    </custom-alert> -->
  <product-list :products="filteredProducts" />
</section>
</template>

<script>
// @ is an alias to /src
import ProductList from '../components/ProductList.vue'
import RangeSelector from '../components/RangeSelector.vue'

export default {
    name: 'Home',
    data:function(){
      return{
        max:50,

      }
    },
    props:['products'],

    components: {
        RangeSelector,
        ProductList
    },
    computed: {
        filteredProducts() {
            return this.products.filter((item) => item.price < Number(this.max))
        },

    },
    methods: {

    },
}
</script>

<template>
    <div class="container">
        <div class="row">
            <h2 class="display-2">Products</h2>
        </div>
        <div class="row justify-content-center gap-3" v-if="products">
            <div v-for="product in products"  class="card" style="width: 18rem;" :key="product.productID">
                <img :src="product.image" class="card-img-top" :alt="product.productName">
                <div class="card-body">
                  <h5 class="card-title">{{product.productName}}</h5>
                  <p class="card-text">
                    <span>email address:{{product.category}}</span>
                  </p>
                  <h5 class="card-title">{{product.amount}}</h5>
                </div>
              </div>
        </div>
        <div v-else class="row">
            <SpinnerCompVue/>
        </div>
    </div>
</template>

<script>
import SpinnerCompVue from '../components/SpinnerComp.vue'
    export default {
        components:{
            SpinnerCompVue
        },
        computed:{
            products(){
                return this.$store.state.products
            }
        },
        // rendering component to the browser
        mounted(){
            this.$store.dispatch('fetchProducts')
        }
    }
</script>

<style scoped>

</style>
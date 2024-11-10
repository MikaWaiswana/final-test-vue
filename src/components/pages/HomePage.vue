<template>
    <div class="align-items-center d-flex img1">
        <div class="card mb-3 ms-5" style="width: 18rem;">
            <div class="card-body">
                <h3 class="card-title">Ready to declutter you closet?</h3>
                <a href="#" class="btn btn-primary" style="min-width: 100%; margin-top: 40px;" id="button-card">Shop Now</a>
            </div>
        </div>
    </div>
    <div class="container-md my-5">
        <div class="d-flex justify-content-between align-items-center">
            <div class="popular__title">
                <h2>Popular items</h2>
            </div>
            <div>
                <router-link to="/product-list-all" style="color: darkgreen; text-decoration: none;">See all</router-link>
            </div>
        </div>
        <product-list
        :products="productList"
        v-if="productListStatus">
        </product-list>
    </div>
    <!-- Tambahkan Section untuk Shop by Category -->
    <div class="container-md my-5">
        <div class="d-flex flex-wrap mb-3">
            <div>
                <h2>Shop by Category</h2>
            </div>
        </div>
        <product-category
        :products="productList"
        v-if="productListStatus">
        </product-category>
    </div>
    <div class="container-md my-5">
        <div class="d-flex justify-content-between align-items-center">
            <div class="popular__title">
                <h2>New Product</h2>
            </div>
            <div>
                <router-link to="/product-list-all" style="color: darkgreen; text-decoration: none;">See all</router-link>
            </div>
        </div>
        <product-list
        :products="productList"
        v-if="productListStatus">
        </product-list>
    </div>
</template>

<script setup>
import ProductList from '../product/ProductList.vue';
import ProductCategory from '../product/ProductCategory.vue';
import { onMounted, ref } from "vue";
import { useStore } from "vuex";

const store = useStore();
const productListStatus = ref(false);
const productList = ref();

onMounted(async () => {
    try {
        await store.dispatch("product/getProductData");
        productListStatus.value = true;
        productList.value = store.state.product.products;
    } catch (error) {
        console.log(error);
    }
});
</script>
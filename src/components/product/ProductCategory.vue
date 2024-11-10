<template>
    <div class="container">
        <div class="d-flex flex-wrap brand-list">
        <button class="btn btn-category btn-outline-secondary me-2">Zip Hoodie</button>
        <button class="btn btn-category btn-outline-secondary me-2">Tee</button>
        <button class="btn btn-category btn-outline-secondary me-2">Shoes</button>
        <button class="btn btn-category btn-outline-secondary me-2">Slippers</button>
      </div>
    </div>
</template>

<script setup>
import product from '@/store/product';

defineProps({
    products: Array
})
</script>

<style scoped>
.btn-category {
    color: darkgreen
}

.btn-category:hover {
    background-color: darkgreen;
    color: white;
}
</style>
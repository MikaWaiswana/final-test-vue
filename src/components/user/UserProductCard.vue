<template>
    <div class="col-md-6 col-12 my-2">
        <div class="card">
            <div class="card-body">
                <div class="d-flex justify-content-between">
                    <div>
                    <p class="mb-0">{{ product.category }}</p>
                    <div class="h-50">
                        <h4 class="fs-5 mb-0">{{ product.name }}</h4>
                    </div>
                    <slot></slot>
                    </div>
                    <div class="d-flex">
                    <img :src="product.image" :alt="product.name" width="90" height="80" class="rounded" style="object-fit: cover">
                    </div>
                </div>
                <div class="d-flex justify-content-between mt-3 pt-3 border-top">
                    <button class="btn delete-btn px-3 py-2 border"
                    style="background-color: darkred; color: white;"
                    @click="$emit('btnRemowe')">
                    {{ buttonName[0] }}
                    </button>
                    <button class="btn edit-btn px-3 py-2 border"
                    style="background-color: darkgreen; color: white;"
                    @click="$emit('btnUpdate')">
                    {{ buttonName[1] }}
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
defineProps({
  product: { type: Object, require: true },
  buttonName: { type: Array, require: true }
})
</script>
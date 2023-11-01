<template>
    <div class="col-md-4">
        <img
            :src="image_url"
            :alt="brand"
            class="product__image"
            loading="lazy" style="max-width:100%;height:300px;"
        />
        <div class="product__header">
            <span class="brand">{{ brand }}</span>
        </div>
        <p class="product__name">{{ productName }}</p>
        <div class="rating">
            <i v-for="rating in ratings" :key="rating" class="fas fa-star"></i>
        </div>
        <div class="price">
            <span>Price: {{ price }}$</span>
        </div>
        <button
                class="btn primary"
                @click="goToProductDetails(productId)"
            > 
            View Details
        </button>
    </div>
</template>

<script>
export default {
    name: "ProductCard",
    props: [
        "productId",
        "image_url",
        "brand",
        "productName",
        "price",
        "ratings"
    ],
    methods:{
        goToProductDetails (productId){
             this.$router.push('/cart/' + productId)
        }
    }
};
</script>
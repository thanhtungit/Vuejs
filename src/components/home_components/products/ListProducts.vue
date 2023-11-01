<template>
    <section class="container products">
        <h2 style="text-align: center;margin-bottom: 20px;">List Products</h2>
        <div class="container">
            <div class="row" v-if="listProducts">
                <product-card
                    v-for="(product, index) in listProducts"
                    :key="index"
                    :productId="product.id"
                    :productName="product.title"
                    :brand="product.category"
                    :price="product.price"
                    :ratings="product.rating"
                    :image_url="product.image"
                />
            </div>
            <product-preloader type="inline" v-else>
                Loading products...
            </product-preloader>
        </div>
    </section>
</template>

<script>
import ProductCard from "@/components/home_components/cards/ProductCard.vue";
import ProductPreloader from "@/components/preloaders/ProductPreloader.vue";
export default {
    name: "listProducts",
    components: {
        ProductCard,
        ProductPreloader,
    },
    props: ["listProducts"],
};
</script>

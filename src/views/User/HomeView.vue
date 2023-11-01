<template>
    <main-header />
    <banner-section />
    <list-products :listProducts="listProducts" />
    <main-footer />
</template>

<script>
import BannerSection from "@/components/home_components/BannerSection.vue";
import ListProducts from "@/components/home_components/products/ListProducts.vue";
import AdvertSection from "@/components/home_components/AdvertSection.vue";
import ActionButton from "@/components/ActionButton.vue";
import MainHeader from "@/components/MainHeader.vue";
import MainFooter from "@/components/MainFooter.vue";

import axios from "axios";

export default {
    name: "HomeView",
    data() {
        return {
            products: [],
        };
    },
    methods: {
       
    },
    components: {
        BannerSection,
        ListProducts,
        ActionButton,
        MainHeader,
        MainFooter,
    },
    computed: {
        listProducts() {
            return this.products;
        },
    },
    async created() {
        let res1 = await axios.get("https://fakestoreapi.com/products?limit=6");
        if (res1.data && res1.data.length>0) {
            this.products = res1.data
        }
    },
};
</script>

<style scoped>
/* Hero Section */
.hero__section {
    display: flex;
    align-items: center;
    justify-content: center;
    height: calc(100vh - 65px);
    background-image: url("@/assets/images/hero4.webp");
    background-position: 60% 30%;
    background-size: cover;
}

.hero__text {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
}

.hero__text h4 {
    padding-bottom: 1rem;
}

.hero__text h1 {
    color: var(--dim-blue);
}

.hero__text p {
    margin-bottom: 1rem;
}

@media (min-width: 2000px) {
    .hero__section {
        background-position: 70% 12%;
        background-size: contain;
        background-repeat: no-repeat;
        background-color: #e3e6f3;
        height: 50vh;
    }
}

@media (min-width: 3000px) {
    .hero__section {
        background-position: 60% 30%;
        /* background-size: cover; */
    }
}
</style>

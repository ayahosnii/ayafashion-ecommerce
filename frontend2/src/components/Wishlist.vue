<template>
        <!--====== Section 1 ======-->
        <div class="u-s-p-y-60">

            <!--====== Section Content ======-->
            <div class="section__content">
                <div class="container">
                    <div class="breadcrumb">
                        <div class="breadcrumb__wrap">
                            <ul class="breadcrumb__list">
                                <li class="has-separator">

                                    <a href="index.html">Home</a></li>
                                <li class="is-marked">

                                    <a href="wishlist.html">Wishlist</a></li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <!--====== End - Section 1 ======-->


        <!--====== Section 2 ======-->
        <div class="u-s-p-b-60">

            <!--====== Section Intro ======-->
            <div class="section__intro u-s-m-b-60">
                <div class="container">
                    <div class="row">
                        <div class="col-lg-12">
                            <div class="section__text-wrap">
                                <h1 class="section__heading u-c-secondary">Wishlist</h1>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <!--====== End - Section Intro ======-->


            <!--====== Section Content ======-->
            <div class="section__content">
                <div class="container">
                    <div class="row">
                        <div class="col-lg-12 col-md-12 col-sm-12">

                            <!--====== Wishlist Product ======-->
                            <div v-for="item in items" class="w-r u-s-m-b-30">
                                <div class="w-r__container">
                                    <div class="w-r__wrap-1">
                                        <div class="w-r__img-wrap">

                                            <img v-for="image in items.images" class="u-img-fluid" :src="`/assets/images/product/${image.photo}`" alt=""></div>
                                        <div class="w-r__info">

                                                <span class="w-r__name">

                                                    <a href="product-detail.html">{{ item.name }}</a></span>

                                            <span class="w-r__category">

                                                    <a href="shop-side-version-2.html">Electronics</a></span>

                                            <span class="w-r__price">$125.00

                                                    <span class="w-r__discount">$160.00</span></span></div>
                                    </div>
                                    <div class="w-r__wrap-2">

                                        <a class="w-r__link btn--e-brand-b-2" data-modal="modal" data-modal-id="#add-to-cart">ADD TO CART</a>

                                        <a class="w-r__link btn--e-transparent-platinum-b-2" href="product-detail.html">VIEW</a>

                                        <a class="w-r__link btn--e-transparent-platinum-b-2" href="#">REMOVE</a></div>
                                </div>
                            </div>
                            <!--====== End - Wishlist Product ======-->
                        </div>
                        <div class="col-lg-12">
                            <div class="route-box">
                                <div class="route-box__g">

                                    <a class="route-box__link" href="shop-side-version-2.html"><i class="fas fa-long-arrow-alt-left"></i>

                                        <span>CONTINUE SHOPPING</span></a></div>
                                <div class="route-box__g">

                                    <a class="route-box__link" href="wishlist.html"><i class="fas fa-trash"></i>

                                        <span>CLEAR WISHLIST</span></a></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <!--====== End - Section Content ======-->
        </div>
        <!--====== End - Section 2 ======-->
</template>
<script>
import axios from 'axios';

export default {
    data() {
        return {
            items: [],
            subtotal: [],
            errorMessage: [],
        }
    },
    mounted() {
        this.fetchData()
    },
    methods: {
        async fetchData() {
            const response = await axios.get("http://127.0.0.1:8000/api/wish-list")
            this.items =  response.data
        }
    }
}
</script>
<style>

</style>

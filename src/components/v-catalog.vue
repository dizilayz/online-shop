<template>
<div class="v-catalog">
    <h1>Catalog</h1>
    <div class="v-catalog-list">
        <vCatalogItem 
        v-for="product in PRODUCTS" 
        :key="product.article" 
        :product_data="product" 
        @addToCart=addToCart 
        />
    </div>
</div>
</template>

<script>
import vCatalogItem from './v-catalog-item.vue';
import {
    mapActions,
    mapGetters
} from 'vuex';

export default {
    name: 'v-catalog',
    components: {
        vCatalogItem
    },
    props: {},
    data() {
        return {}
    },
    computed: {
        ...mapGetters([
            'PRODUCTS'
        ])
    },
    methods: {
        ...mapActions([
            'GET_PRODUCTS_FROM_API',
            'ADD_TO_CART',
        ]),
        addToCart: function (data) {
            this.ADD_TO_CART(data)
        }
    },
    watch: {},
    mounted() {
        this.GET_PRODUCTS_FROM_API()
    }
}
</script>

<style lang="scss">
.v-catalog {
    &-list {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        align-items: center;
    }
}
</style>

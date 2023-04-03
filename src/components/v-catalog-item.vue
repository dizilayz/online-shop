<template>
<div class="v-catalog-item">
    <img class="v-catalog-item_image" :src=" require('../assets/images/' + product_data.image) " alt="img">
    <p class="v-catalog-item_name">
        {{ product_data.name }}</p>
    <p class="v-catalog_price"> Price: {{
            product_data.price }} ₽</p>
    <button 
        class="v-catalog_add_to_cart_btn btn"
        @click="sendDataToParent"
        >add to cart
    </button>
</div>
</template>

<script>
export default {
    name: 'v-catalog-item',
    components: {},
    props: {
        product_data: {
            type: Object,
            default () {
                return {}
            }
        }
    },
    data() {
        return {

        }
    },
    computed: {},
    methods: {
        sendDataToParent: function () {
            this.$emit('sendDataToParent', this.product_data.article)
        }
    },
    watch: {},
    mounted() {

    }
}
</script>

<style lang="scss">
.v-catalog-item {
    flex-basis: 25%;
    flex-shrink: 0;
    box-shadow: 0 0 8px 0;
    padding: $padding*2;
    margin-bottom: $margin*2;

    &_image {
        width: 100px;
        height: 150px;
    }
}
</style>

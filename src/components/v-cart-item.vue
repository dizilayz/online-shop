<template>
<div class="v-cart-item">
    <img class="v-cart-item_image" :src="require('../assets/images/' + cart_item_data.image)" alt="img">
    <div class="v-cart-item_info">
        <p> {{ cart_item_data.name }} </p>
        <p>Price: {{ cart_item_data.price }}</p>
        <p> {{ cart_item_data.article }} </p>
    </div>
    <div class="v-cart-item_quantity">
        <p>Quantity:</p>
        {{cart_item_data.quantity}}
    </div>
    <div class="v-cart-item_quantity">
        <button @click="deleteFromCart">Delete</button>
    </div>
</div>
</template>

<script>
import {
    ref,
    watchEffect
} from 'vue'

export default {
    name: 'v-cart-item',
    components: {},
    props: {
        cart_item_data: {
            type: Object,
            default () {
                return {}
            }
        }
    },
    setup(props) {
        const cartItemData = ref(props.cart_item_data)

        watchEffect(() => {
            cartItemData.value.quantity = 1
        })

        return {
            cartItemData
        }
    },
    data() {
        return {

        }
    },
    computed: {},
    methods: {
        deleteFromCart: function() {
            this.$emit('deleteFromCart')
        }
    },
    watch: {},
    mounted() {}
}
</script>

<style lang="scss">
.v-cart-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: nowrap;
    box-shadow: 0 0 8px 0;
    padding: $padding*2;
    margin-bottom: $margin*2;

    &_image {
        max-width: 100px;
    }
}
</style>

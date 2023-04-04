<template>
    <div class="vCart">
        <h1>Cart</h1>
        <vCartItem
        v-for="(item, index) in cart_data" 
        :key="item.article"
        :cart_item_data="item"
        @deleteFromCart="deleteFromCart(index)"
        />
    </div>
</template>
<script>
import vCartItem from './v-cart-item.vue';
import { mapActions } from 'vuex';

export default {
    components: {
        vCartItem,
    },
    props: {
        cart_data: {
            type: Array,
            default() {
                return []
            }
        }
    },
    methods: {
        ...mapActions([
        'DELETE_FROM_CART'
        ]),
        deleteFromCart: function(index) {
            this.DELETE_FROM_CART(index)
        }
    }
}
</script>
<style lang="">
    
</style>
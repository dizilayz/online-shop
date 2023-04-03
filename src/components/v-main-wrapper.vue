<template>
    <div class="v-main-wrapper">
        <vCatalog/>
        <vCart/>
    </div>
</template>

<script>
import vCatalog from './v-catalog.vue';
import vCart from './v-cart.vue';
    export default {
        name: 'v-main-wrapper',
        components: {
            vCatalog,
            vCart
        },
        props: {},
        data() {
            return{
                title: 'Main wrapper'
            }
        },
        computed:{},
        methods: {},
        watch:{},
        mounted() {
            console.log('done')
        }
    }
</script>

<style lang="scss">
    .v-main-wrapper {
        max-width: 900px;
        margin: 0 auto;
    }
</style>
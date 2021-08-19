<template>
    <div id="productlistone">
        <h2>Product List One</h2>
        <div class="p-list">
            <ul v-for="product in saleProducts" :key="product">
                <li>
                    <span class="name">{{ product.name }}</span>
                    <span class="price">${{ product.price}}</span>
                </li>
            </ul>
            <button @click="reducePrice(6)">Reduce Price</button>
        </div>
    </div>
</template>

<script>
import { mapState, mapActions, mapGetters } from 'vuex'
export default {
    computed: {
        /* products() {
           return this.$store.state.products
        }, */

        ...mapState([
            'products'
        ]),

        /* saleProducts() {
            return this.$store.getters.saleProducts
        } */

        ...mapGetters([
            'saleProducts'
        ])
    },

    methods: {
        // reducePrice(amount) {
        //     /* this.$store.state.products.forEach( product => {
        //         product.price -= 1
        //     }) */

        //     //this.$store.commit('reducePrice')  // this will perform direct mutations
        //     this.$store.dispatch('reducePrice', amount)  // this will perform an specific action during mutaions
        // }
        ...mapActions([
            'reducePrice'
        ])
    }
}
</script>

<style scoped>
    #productlistone {
        background: #fff8b1;
        box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
        margin-bottom: 30px;
        padding: 10px 20px;
    }

    #productlistone ul {
        padding: 0;
    }

    #productlistone li {
        display: inline-block;
        margin-left: 10px;
        margin-top: 10px;
        padding: 20px;
        background: rgba(225, 225, 225, 0.7);
    }

    .price {
        font-weight: bold;
        color: #E8800c;
    }
</style>
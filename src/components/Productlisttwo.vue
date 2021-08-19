<template>
    <div id="productlisttwo">
        <h2>Product List Two</h2>
        <div class="p-list">
            <ul v-for="product in saleProducts" :key="product">
                <li>
                    <span class="name">{{ product.name }}</span>
                    <span class="price">${{ product.price }}</span>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex'
export default {
    computed: {
        /* products() {
            return this.$store.state.products
        },*/

        ...mapState([
            'products'
        ]),

        /*saleProducts() {
            return this.$store.getters.saleProducts
        }*/

        ...mapGetters([
            'saleProducts'
        ])
    }
}
</script>

<style>
    #productlisttwo {
        background: #D1E4FF;
        box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
        margin-bottom: 30px;
        padding: 10px 20px;
    }

    #productlisttwo ul {
        padding: 0;
        list-style-type: none;
    }

    #productlisttwo li {
        margin-left: 10px;
        margin-top: 10px;
        padding: 20px;
        background: rgba(225, 225, 225, 0.7);
    }

    .price {
        font-weight: bold;
        color: #860CE8;
        display: block;
    }
</style>
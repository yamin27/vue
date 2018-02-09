<template>
    <div id="app">
        <navbar></navbar>
        <div class="container">
            <div class="row">
                <div class="col-md-9">
                    <inventory @newItemAdded="addCartItem" :items="items"></inventory>
                </div>
                <div class="col-md-3">
                    <cart :items="cart"></cart>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Navbar from './components/Navbar'
    import Cart from  './components/Cart'
    import Inventory from './components/Inventory'
    import data from './data'

    export default {
        components: {
            Navbar, Cart, Inventory
        },
        data() {
            return {
                items: [],
                cart: [{
                    id: 2,
                    title: 'Bangla Khabar',
                    price: 12.60,
                    photo: "http://dummyimage.com/127x184.png/cc0000/ffffff",
                }]
            }
        },
        mounted(){
            this.items = data
            // console.log(data);
        },
        methods : {
            addCartItem(item){
                this.cart.push(item)
            }
        }
    }
</script>

<style>
.container {
    padding-top: 10px;
}

</style>

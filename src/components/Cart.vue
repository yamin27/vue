<template>

        <ul class="list-group">
            <li v-for="(item, index) in items" :key="index" class="list-group-item">
               <span class="item-name">{{item.title}}</span>
               <button class="btn btn-sm btn-danger" @click="removeItem(index)">-</button>
               <span class="item-price float-right">{{item.price}}</span>
            </li>
            <li class="list-group-item">
                <span class="item-name">Total :</span>
                <span class="item-">{{totalPrice}}</span>
            </li>
        </ul>
</template>

<script>
    export default {
        name: "cart",
        props: ['items'],
        computed: {
            totalPrice(){
                let total = 0;
                this.items.forEach(item => {
                    total += parseFloat(item.price)
                })
                return total;
            }
        },
        methods:{
            removeItem(index){
                this.$emit('removeItem', index)
            }
        }
    }
</script>

<style scoped>

</style>
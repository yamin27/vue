<template>

<div class="row">
    <div v-for="(item, index) in items" :key= "index" class="card" style="width: 18rem;">
        <img class="card-img-top" :src="item.photo" alt="Card image cap">
        <div class="card-body">
            <h5 class="card-title">{{item.title}}</h5>
            <p class="card-text">{{item.price}}</p>
            <a href="#" @click="addToCart(item)" class="btn btn-primary">+ add</a>
        </div>
    </div>
</div>
</template>

<script>
    export default {
        name: "inventory",
        props : ['items'],
        methods:{
            addToCart(item){
                this.$emit('newItemAdded', item)
            }
        }
    }
</script>

<style scoped>

</style>
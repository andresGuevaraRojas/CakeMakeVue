<template>
    <section class="container-horizontalPadding">
        <h2>Sabores</h2>
        <div class="flavors">
            <CardItem v-for="flavor in flavors" :key="flavor.name" :image="flavor.image" :name="flavor.name" :description="flavor.description"/>
        </div>        
    </section>
</template>

<script>

import CardItem from './CardItem.vue'
export default {
    name:'FlavorSection',
    data(){
        return{
            flavors:[
                {
                    image:require('@/assets/images/fresa.jpg'),
                    name:'Fresa',
                    description:'$100.00'
                },
                {
                    image:require('@/assets/images/chocolate.jpg'),
                    name:'Chocolate',
                    description:'$200.00'
                },
                {
                    image:require('@/assets/images/vainilla.jpg'),
                    name:'Vainilla',
                    description:'$100.00'
                }
            ]
        }
    },
    components:{
        CardItem
    }    
}
</script>
<style scoped>
    h2{
        text-align: center;
    }
    .flavors{
        display: flex;
        justify-content: space-around;
    }
</style>
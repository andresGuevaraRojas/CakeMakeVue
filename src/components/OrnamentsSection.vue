<template>
    <section class="container-horizontalPadding">
        <h2>Decoraciones</h2>
        <div class="organents">
            <CardItem v-for="organent in organents" :key="organent.name" :image="organent.image" :name="organent.name" :description="organent.description"/>
        </div>        
    </section>
</template>

<script>

import CardItem from './CardItem.vue'
export default {
    name:'OrnamentsSection',
    data(){
        return{
            organents:[
                {
                    image:require('@/assets/images/letrero.jpg'),
                    name:'Letrero',
                    description:'$20.00'
                },
                {
                    image:require('@/assets/images/merengue.jpg'),
                    name:'Merengue',
                    description:'$50.00'
                },
                {
                    image:require('@/assets/images/dulce.jpg'),
                    name:'Dulce',
                    description:'$60.00'
                },
                {
                    image:require('@/assets/images/frutas.jpg'),
                    name:'Frutas',
                    description:'$80.00'
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
    .organents{
        display: flex;
        justify-content: space-around;
    }

    
</style>
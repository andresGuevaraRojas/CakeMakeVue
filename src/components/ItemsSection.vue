<template>
    <section class="container-horizontalPadding section">
        <h2>{{title}}</h2>
        <div class="items">
            <slot></slot>
        </div>        
    </section>
</template>

<script>


export default {
    name:'ItemsSection',
    props:{
        title:String        
    },
    data(){
        return{}            
    },      
}
</script>
<style scoped>
    .section{
        padding-top:1em;
        padding-bottom:1em;
    }
    h2{
        text-align: center;
    }
    .items{
        display: flex;
        justify-content: space-around;
    }

    
</style>
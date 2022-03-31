<template>
    <div class="container" :style="{maxWidth:maxWidth}">
        <div class="content">
            <img :src='image'>
        </div>
        <div class="footer">
            <slot>
                <span>{{name}}</span>
                <span>{{description}}</span>    
            </slot>            
        </div>
    </div>
</template>
<script>
export default {
    name:'CardItem',
    props:{
        image:String,
        name:String,
        description:String,
        maxWidth:{
            type:String,
            default:'320px'
        }
    }
}
</script>

<style scoped>
    .container{
        min-width: 200px;
        max-width: 320px;
    }
    .content img{
        width: 100%;
        display: block;
    }
    .footer{
        border: 2px solid #F2C8C4;
        padding: 4px;
    }
    .footer span{
        display: block;
        text-align: center;
    }
</style>
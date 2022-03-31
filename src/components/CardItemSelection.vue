<template>
    <div class="container">
        <div class="content">
            <span>{{name}}</span>
            <img :src='image'>
        </div>
        <div class="footer">            
            <input
                type="checkbox"
                name="group"                
                :value='name'
            />          
        </div>
    </div>
</template>
<script>
export default {
    name:'CardItemSelection',
    props:{
        image:String,
        name:String,
        group:String     
    }
}
</script>

<style scoped>
    .container{
        width: 120px;
        margin-right: 16px;
    }
    .container:last-child{
        margin-right: 0;
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
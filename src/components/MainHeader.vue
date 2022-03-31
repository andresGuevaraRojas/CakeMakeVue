<template>
    <header id="#inicio">
        <div class="descriptionContainer container-horizontalPadding">
            <h1>Crea el pastel de tus sueños</h1>
            <p>Tenemos a tu disposición una gran variedad de sabores y de decoraciones para hacer de tu pastel único</p>
            <button>Crear mi pastel</button>
        </div>
        <div class="imageContainer">
            <img src='../assets/images/ChocolateCake.jpg' alt="">
        </div>
    </header>
</template>

<script>
export default {
    name:'MainHeader'
}
</script>

<style scoped>
    header{
        display: flex;
    }
    header div{
        width: 50%;
    }
    .descriptionContainer{
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
    h1{
        margin-top: 0;
        margin-bottom: 0.6rem;
    }
    .descriptionContainer p{
        margin-top: 0;
        margin-bottom: 2rem;
        max-width: 400px;
    }
    .descriptionContainer button{
        max-width: 200px;
        padding: 1em;
        min-width: 40px;
        background-color:#8469BF;
        color: white;
        border: none;
        cursor: pointer;
    }
    .imageContainer img{
        width: 100%;
    }
</style>
<template>
  <router-view/>
</template>

<style>
:root{
  --navBar-height:100px;  
}
*,::before,::after{
  box-sizing: border-box;
}
body{
  margin: 0;
  padding: 0;    
  min-height: 100vh;
  width: 100%;
  font-family: Roboto,serif;
  background-color: #f5f5f5;  
}
h1{
  font-size: 1.6em;
}
h2{
  font-size: 1.5em;
  font-family: 'Dancing Script', cursive;
}

main{
  margin-top: var(--navBar-height);
}
.container-horizontalPadding{
  padding-left: 1em;
  padding-right: 1em;
}

</style>

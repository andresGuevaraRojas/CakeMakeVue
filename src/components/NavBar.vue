<template>
  <nav>
    <img
      src="../assets/CakeMakeLogo.png"
      alt="CakeMake logo"      
    />
    <p>CakeMake</p>
    <ul>
      <li v-for="link in links" :key="link.name"><router-link :to='link.path'>{{link.name}}</router-link></li>      
    </ul>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  props:{
    links:Array
  }
};
</script>

<style scoped>
nav {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 0.5em 1em;
  background-color: white;
  border: 1px solid #c3c3c3;
  margin: 0;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: var(--navBar-height);
}
img{
    width: 80px;
}
p{
  position: absolute;
  font-size: 1.6em;
  left: 50%;
  transform: translate(-50%);
  font-family: 'Dancing Script', cursive;
}
ul{
  display: flex;
  list-style: none;
  padding: 0;
  margin: 0;  
}
li{
  margin-left: 10px;
}
li:first-child{
  margin-left: 0;
}
a{
  text-decoration: none;
  color: black;
}
</style>
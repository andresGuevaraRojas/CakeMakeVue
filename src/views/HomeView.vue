<template>
  <NavBar :links="links"/>
  <main>
    <MainHeader/>
    <FlavorSection />
    <OrnamentsSection />
    <FormCake />
    <FooterSection />
  </main>
</template>

<script>
import NavBar from "@/components/NavBar.vue";
import MainHeader from "@/components/MainHeader.vue";
import FlavorSection from "@/components/FlavorsSection.vue";
import OrnamentsSection from "@/components/OrnamentsSection.vue";
import FormCake from "@/components/FormCake.vue";
import FooterSection from "@/components/FooterSection.vue";
export default {
  name: "HomeView",
  components: {
    NavBar,
    MainHeader,
    FlavorSection,
    OrnamentsSection,
    FormCake,
    FooterSection,
  },
  data(){
    return{
      links:[
        {path:'/#inicio',name:'Inicio'},
        {path:'/baker',name:'Iniciar sesión'},
        {path:'/#contacto',name:'Contacto'}
      ]
    }
  }
};
</script>


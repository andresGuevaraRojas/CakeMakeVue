<template>
  <NavBar :links="links" />
  <main>
    <ItemsSection title="Inventario de sabores">
      <CardItem
        v-for="flavor in flavorsStock"
        :key="flavor.name"
        :image="flavor.image"
        maxWidth="160px"
      >
        <span class="infoCard">{{ flavor.name }}</span>
        <span class="infoCard">{{ flavor.price }}</span>
        <span :class="classObject(flavor.count)"
          >Unidades disponibles: {{ flavor.count }}</span
        >
      </CardItem>
    </ItemsSection>
    <ItemsSection title="Inventario de decoraciones">
      <CardItem
        v-for="ornament in ornamentsStock"
        :key="ornament.name"
        :image="ornament.image"
        maxWidth="160px"
      >
        <span class="infoCard">{{ ornament.name }}</span>
        <span class="infoCard">{{ ornament.price }}</span>
        <span :class="classObject(ornament.count)"
          >Unidades disponibles: {{ ornament.count }}</span
        >
      </CardItem>
    </ItemsSection>
    <section class="container-horizontalPadding pedidos">
        <h2>Pedidos</h2>                
        <div class="container__content">
          <TableOrders :headers='headers' :data="data"/>
        </div>        
    </section>

    <FooterSection />
  </main>
</template>

<script>
import NavBar from "@/components/NavBar.vue";

import FooterSection from "@/components/FooterSection.vue";
import ItemsSection from "@/components/ItemsSection.vue";
import CardItem from "@/components/CardItem.vue";
import TableOrders from "@/components/TableOrders.vue"
export default {
  name: "BakerView",
  components: {
    NavBar,
    FooterSection,
    ItemsSection,
    CardItem,
    TableOrders
  },
  data() {
    return {
      links: [
        { path: "#inicio", name: "Inicio" },
        { path: "#", name: "Andrew" },
        { path: "/", name: "Cerrar sesión" },
        { path: "#contacto", name: "Contacto" },
      ],
      flavorsStock: [
        {
          image: require("@/assets/images/fresa.jpg"),
          name: "Fresa",
          price: "$100.00",
          count: 30,
        },
        {
          image: require("@/assets/images/chocolate.jpg"),
          name: "Chocolate",
          price: "$200.00",
          count: 5,
        },
        {
          image: require("@/assets/images/vainilla.jpg"),
          name: "Vainilla",
          price: "$100.00",
          count: 10,
        },
      ],
      ornamentsStock: [
        {
          image: require("@/assets/images/letrero.jpg"),
          name: "Letrero",
          price: "$20.00",
          count: 25,
        },
        {
          image: require("@/assets/images/merengue.jpg"),
          name: "Merengue",
          price: "$50.00",
          count: 32,
        },
        {
          image: require("@/assets/images/dulce.jpg"),
          name: "Dulce",
          price: "$60.00",
          count: 6,
        },
        {
          image: require("@/assets/images/frutas.jpg"),
          name: "Frutas",
          price: "$80.00",
          count: 4,
        },
      ],      
      headers:[
        'Nombre',
        'Teléfono',
        'Correo electrónico',
        'Sabores',
        'Decoraciones',
      ],
      data:[
        {
          cliente:'José R',
          telefono:'+524444',
          correo:'joser@fakemail.com',
          sabores:['Chocolate','Vainilla'],
          decoraciones:['Letrero']        
        },
        {
          cliente:'Teresa F',
          telefono:'+554656432',
          correo:'teresa_f3344@fakemail.com',
          sabores:['Fresa','Vainilla'],
          decoraciones:['Merengue','Frutas']        
        },   
        {
          cliente:'Jimena N',
          telefono:'+5245454366',
          correo:'jimenan_1990@fakemail.com',
          sabores:['Chocolate'],
          decoraciones:['Merengue','Letrero']        
        }           
      ],
      classObject(number){
            return{
                green:number>24,
                yellow:number>9 && number<=24,
                red:number<=9,
                infoCard:true
            }
        }
    };
  },    
};
</script>

<style scoped>
.pedidos{
  margin-bottom: 2em;
}
.infoCard {
  display: block;
  text-align: center;
}
h2{
  text-align: center;
}
.green {
  background-color: green;
  color: white;
}
.yellow {
  background-color: yellow;
}
.red {
  background-color: red;
  color: white;
}
.container__content{
  display: flex;
  justify-content: center;
}
</style>
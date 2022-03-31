<template>
  <section class="pedido">
    <h1 class="pedido__title" id="crearpastel">Crear mi pastel</h1>

    <form class="pedido__form">
      <fieldset>
        <legend>Datos de contacto</legend>
        <div class="pedido__form__inputGroup">
          <label>Nombre</label>
          <input type="text" name="nombre" id="nombre" />
        </div>
        <div class="pedido__form__inputGroup">
          <label>Teléfono</label>
          <input type="tel" name="telefono" id="telefono" />
        </div>
        <div class="pedido__form__inputGroup">
          <label>Correo electrónico</label>
          <input type="email" name="email" id="email" />
        </div>
      </fieldset>
      <fieldset>
        <legend>Especificaciones del pastel</legend>
        <div class="pedido__form__inputGroup">
          <label>Descripción general</label>
          <input type="text" name="Descripcion" id="descripcion" />
        </div>
        <div class="pedido__form__checkBoxGroup">
          <p>Selecciona tu sabores favoritos</p>
          <div>
            <CardItemSelection
              v-for="flavor in flavors"
              :key="flavor.name"
              :group="'flavors'"
              :image="flavor.image"
              :name="flavor.name"
            />
          </div>
        </div>
        <div class="pedido__form__checkBoxGroup">
          <p>Selecciona las decoraciones para tu pastel</p>

          <div>
            <CardItemSelection
              v-for="organent in organents"
              :key="organent.name"
              :group="'organents'"
              :image="organent.image"
              :name="organent.name"
            />
          </div>
        </div>
      </fieldset>
      <button type="submit">Ordenar</button>
    </form>
  </section>
</template>

<script>
import CardItemSelection from "./CardItemSelection.vue";
export default {
  name: "FormCake",
  data() {
    return {
      flavors: [
        {
          image: require("@/assets/images/fresa.jpg"),
          name: "Fresa",
          description: "$100.00",
        },
        {
          image: require("@/assets/images/chocolate.jpg"),
          name: "Chocolate",
          description: "$200.00",
        },
        {
          image: require("@/assets/images/vainilla.jpg"),
          name: "Vainilla",
          description: "$100.00",
        },
      ],
      organents: [
        {
          image: require("@/assets/images/letrero.jpg"),
          name: "Letrero",
          description: "$20.00",
        },
        {
          image: require("@/assets/images/merengue.jpg"),
          name: "Merengue",
          description: "$50.00",
        },
        {
          image: require("@/assets/images/dulce.jpg"),
          name: "Dulce",
          description: "$60.00",
        },
        {
          image: require("@/assets/images/frutas.jpg"),
          name: "Frutas",
          description: "$80.00",
        },
      ],
    };
  },
  components: {
    CardItemSelection,
  },
};
</script>
<style scoped>
.pedido {
  display: flex;
  align-items: center;
  flex-direction: column;
}
.pedido__form {
  padding: 2em;
}
.pedido__form fieldset {
  border: none;
  margin: 0;
  padding: 0;
}

.pedido__form fieldset legend {
  background-color: #8469bf;
  color: white;
  margin-bottom: 0.4em;
}
.pedido__title {
  text-align: center;
  font-family: "Dancing Script", cursive;
  font-size: 1.8em;
}

.pedido__form__inputGroup label,
.pedido__form__inputGroup input {
  margin-bottom: 0.4em;
  display: block;
  width: 100%;
}
.pedido__form__checkBoxGroup {
  margin-bottom: 0.6em;
  text-align: center;
}
.pedido__form__checkBoxGroup > div {
  display: flex;
  justify-content: space-between;
}
.pedido__form__checkBoxGroup label,
.pedido__form__inputGroup input {
  display: inline;
}
.pedido__form__checkBoxGroup p {
  margin: 0;
  margin-bottom: 0.5em;
}

.pedido__form button {
  min-width: 80px;
  width: 100%;
  padding: 1em;
  background-color: black;
  color: white;
  border: none;
  cursor: pointer;
}
input {
  padding: 0.5em;
}
input[type="checkbox"] {
  background-color: green;
}
</style>
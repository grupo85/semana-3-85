<template>
  <div id="app">
    <h3 id="api-noticia" class="text-center pt-3 mt-1 font">Últimas noticias</h3>
    <div class="container-fluid shadow-sm">
      <api-component></api-component>
    </div>

    <div class="container-fluid">
      <h3 id="equipo" class="text-center pt-3 mt-1 font">¿Quiénes somos?</h3>
      <div class="row justify-content-center mb-5">
        <div class="col mt-2" v-for="(item, index) of team" :key="index">
          <team-card v-bind:member="item"></team-card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ApiComponent from "./components/ApiComponent.vue";
import TeamCard from "./components/TeamCard.vue";
export default {
  name: "App",
  components: {
    ApiComponent,
    TeamCard,
  },
  data() {
    return {
      team: [
        {
          codigo: 1,
          nombre: "Rodian Burbano",
          descripcion:
            "Rodian tiene 20 años y estudia Ingeniería Civil en la Universidad de Nariño",
          rol: "Desarrollador backend",
          image: "media/Rodian-Burbano.jpeg",
        },
        {
          codigo: 2,
          nombre: "Jenny Vargas Naranjo",
          descripcion:
            "Jenny tiene 32 años y estudia Tecnología en Desarrollo de Software en la UNAD",
          rol: "Desarrollador backend",
          image: "media/Jenny-Vargas.jpeg",
        },
        {
          codigo: 3,
          nombre: "Giovanny Hernández",
          descripcion:
            "Giovanny estudia en la Universidad del Area Andina sede Valledupar",
          rol: "Desarrollador backend",
          image: "media/Giovanny-Hernandez.jpeg",
        },
        {
          codigo: 4,
          nombre: "David Jara Herrera",
          descripcion:
            "David tiene 28 años, tiene 4 semestres de Ingeniería de Sistemas en la Universidad Distrital",
          rol: "Desarrollador backend",
          image: "media/David-Jara.jpg",
        },
      ],
    };
  },
};
</script>
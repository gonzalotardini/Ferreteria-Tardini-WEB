<template >
  <b-container id="nosotros" class="my-5">
    <h1 class="text-center my-5">Sobre Nosotros</h1>
    <p class="text-center mb-5">
      Somos Ferretería Tardini Hnos., una empresa familiar con trayectoria desde
      1994, dedicada a brindar soluciones en ferretería, pinturería, sanitarios,
      herrajes, bulonería, electricidad y bazar. Nos destacamos por ofrecer
      asesoramiento técnico personalizado y productos de calidad a precios
      accesibles. Nuestro compromiso es entender las necesidades de cada cliente
      y aportar la mejor opción con experiencia, cercanía y responsabilidad. En
      Ferretería Tardini, tu problema es nuestro punto de partida para encontrar
      la solución.
    </p>
    <b-row class="pb-3 mt-5">
      <b-col md="4" sm="12" class="text-center">
        <img :src="require('@/assets/usuario.png')" alt="" class="mb-4"/>
        <h5>La mejor atención</h5>
        <p>
          En Ferretería Tardini, nos enorgullece ofrecerte atención personalizada. Nuestro equipo de expertos está listo para brindarte asesoramiento técnico, asegurando que encuentres las herramientas perfectas para cada uno de tus proyectos.
        </p>
      </b-col>
      <b-col md="4" sm="12" class="text-center">
        <img :src="require('@/assets/calidad.png')" alt="" class="mb-4"/>
        <h5>Calidad garantizada</h5>
        <p>
          Solo trabajamos con productos de alta calidad, provenientes de las marcas más confiables, tanto nacionales como internacionales. Sabemos que lo que compres debe durar y rendir al máximo.
        </p>
      </b-col>
      <b-col md="4" sm="12" class="text-center">
        <img :src="require('@/assets/carrito.png')" alt="" class="mb-4"/>
        <h5>Amplia Variedad</h5>
        <p>
          En Ferreteria Tardini, tenemos todo lo que necesitas. Además de una extensa gama de productos de ferretería, también contamos con artículos de sanitarios, bazar, pinturería y mucho más. Encontrá lo que buscas en un solo lugar.
        </p>
      </b-col>
    </b-row>
  </b-container>
</template>
  
  <script>
export default {
  name: "contact",
  components: {},
  data() {
    return {};
  },
};
</script>

  <style scoped>
img {
  max-height: 80%;
  max-width: 80px;
}
</style>
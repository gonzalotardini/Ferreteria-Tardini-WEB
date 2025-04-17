<template>
  <b-container id="nuestrosClientes" class="position-relative py-5" fluid>
    <div class="background-image"></div>
    <div class="content">
      <h1 class="text-center pt-4 pb-5">Nuestros Clientes</h1>
        <b-row>
          <b-carousel
            fade
            v-model="slide"
            :interval="4000"
            controls
            indicators
            background=""
            @sliding-start="onSlideStart"
            @sliding-end="onSlideEnd"
            class="pb-5"
          >
            <b-carousel-slide
              v-for="(group, index) in groupedCards"
              :key="index"
              class="p-2"
            >
              <b-row align-h="center">
                <b-col v-for="(client, i) in group" :key="i" :cols="12" :md="4">
                  <clientCard :client="client" />
                </b-col>
              </b-row>
            </b-carousel-slide>
          </b-carousel>
        </b-row>
        <div class="text-center">
          <b-btn
            href="https://www.google.com.ar/maps/place/Ferreteria+Tardini+Hnos./@-34.5888201,-58.4952651,17z/data=!4m8!3m7!1s0x95bcb64742688765:0xcb658c2d2b9a7b58!8m2!3d-34.5888245!4d-58.4926902!9m1!1b1!16s%2Fg%2F1td0c3ft?entry=ttu&g_ep=EgoyMDI1MDQxNC4xIKXMDSoASAFQAw%3D%3D"
            target="_blank"
            class="custom-btn"
          >
            MIRÁ NUESTRAS RESEÑAS
          </b-btn>
        </div>
      </div>
  </b-container>
</template>
  
  <script>
import clientCard from "./clientCard.vue";

export default {
  name: "clientes",
  components: { clientCard },
  data() {
    return {
      slide: 0,
      sliding: null,
      clients: [
        {
          title: "Juan Almiron",
          description:
            "Excelente ferreteria, tiene de todo. excelente atencion, son muy buena onda, comprensivos y ayudan al cliente con la mejor",
          starts: 5,
          variant: "primary",
        },
        {
          title: "Herbo Botánica",
          description:
            "Nos asesoraron en todos los materiales que tuvimos que comprar para la refacción de nuestro nuevo local y quedamos muy conformes! Muy comprometidos con nuestras necesidades y no nos vendieron por vender, solo lo que necesitamos. 100% recomendable!",
          stars: 5,
          variant: "secondary",
        },
        {
          title: "Daniel Severo",
          description:
            "Tienen de todo, así que es el lugar en el barrio donde concurrir cuando algo falta, algo se rompe o algo hay que renovar. Desde tornillos, burletes, adhesivos, pinturas, etc, etc. Y siempre con la buena atención de sus dueños, muy pacientes con sus clientes.",
          stars: 5,
          variant: "success",
        },
        {
          title: "Imagenes Andinas",
          description:
            "Tienen buenos precios y sobre todo atienden bien y de buenos modos. No estoy cerca pero elijo caminar mas y tener una buena atención.",
          stars: 5,
          variant: "info",
        },
        {
          title: "Martín Gonzalez",
          description:
            "Excelente atención, súper educados y saben sobre lo que ofrecen. Pocos quedan con el nivel de servicio que atienden. Muy buenos precios",
          stars: 5,
          variant: "warning",
        },
        {
          title: "Alicia López",
          description:
            "Excelente atención,  precios y asesoramiento.  Con las expliacciones y ayuda que te dan podes solucionar cualquier problema que tengas en tu casa. Genios!!!!!",
          stars: 5,
          variant: "danger",
        },
      ],
      isMobile: window.innerWidth <= 768,
    };
  },
  computed: {
    groupedCards() {
      const groupSize = this.isMobile ? 1 : 3;
      return this.clients.reduce((acc, curr, i) => {
        if (i % groupSize === 0) acc.push([]);
        acc[acc.length - 1].push(curr);
        return acc;
      }, []);
    },
  },
  methods: {
    onSlideStart() {
      this.sliding = true;
    },
    onSlideEnd() {
      this.sliding = false;
    },
    handleResize() {
      this.isMobile = window.innerWidth <= 768;
    },
  },
  mounted() {
    window.addEventListener("resize", this.handleResize);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.handleResize);
  },
};
</script>
  
<style scoped>
.carousel {
  width: 100% !important;
}
.carousel-item {
  min-height: 400px;
}
.carousel-caption {
  justify-content: center !important ;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}

.background-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url("../assets/tools3.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  z-index: 0;
  filter: blur(2px) brightness(0.5);
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(192, 57, 43, 0.4); /* rojo semitransparente */
  z-index: 1;
}

.content {
  position: relative;
  z-index: 2; /* Ahora el contenido está arriba */
}

.custom-btn {
  background-color: #A93226; /* rojo óxido */
  color: #fff;
  border: none;
  font-weight: bold;
  letter-spacing: 1px;
  padding: 12px 28px;
  transition: all 0.3s ease;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-size: 16px;
}

.custom-btn:hover {
  background-color: #922B21;
  transform: scale(1.05);
}
@media (max-width: 576px) {
  .container-fluid {
    background-size: auto;
  }
}

h1 {
  color: white;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
}
</style>
<template>
  <b-container id="prodcutos" class="position-relative py-5" fluid>
    <div class="content">
      <h1 class="text-center pt-4 pb-5 mb-5">Nuestros Productos</h1>
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
          class="pb-5 mt-2"
        >
          <b-carousel-slide
            v-for="(group, index) in groupedImages"
            :key="index"
            class="p-2 item"
          >
            <div class="d-flex align-items-center justify-content-center h-100">
              <b-row align-h="center" align-v="center">
                <b-col
                  v-for="(img, i) in group"
                  :key="i"
                  cols="12"
                  md="3"
                  class="d-flex justify-content-center align-items-center"
                >
                  <img :src="img.src" :alt="img.alt" class="img-fluid" />
                </b-col>
              </b-row>
            </div>
          </b-carousel-slide>
        </b-carousel>
      </b-row>
      <div class="text-center my-5">
        <b-btn
          href="https://listado.mercadolibre.com.ar/_CustId_83739677"
          target="_blank"
          class="custom-btn"
        >
          CONOCÉ NUESTROS PRODCUTOS ONLINE
        </b-btn>
      </div>
    </div>
  </b-container>
</template>
    
    <script>
export default {
  name: "clientes",
  components: {},
  data() {
    return {
      slide: 0,
      sliding: null,
      isMobile: window.innerWidth <= 768,
      imagenes: [
        { src: require("@/assets/Marcas/alba.jpg"), alt: "Alba" },
        { src: require("@/assets/Marcas/bahco.jpg"), alt: "Bahco" },
        { src: require("@/assets/Marcas/bremen.jpg"), alt: "Bremen" },
        { src: require("@/assets/Marcas/bulit.jpg"), alt: "Bulit" },
        { src: require("@/assets/Marcas/fisher.jpg"), alt: "Fisher" },
        { src: require("@/assets/Marcas/fortex.jpg"), alt: "Fortex" },
        { src: require("@/assets/Marcas/kalop.jpg"), alt: "Kalop" },
        { src: require("@/assets/Marcas/Parsecs.jpg"), alt: "Parsecs" },
        {
          src: require("@/assets/Marcas/blackDecker.jpg"),
          alt: "Black Decker",
        },
        { src: require("@/assets/Marcas/tigre.jpg"), alt: "Tigre" },
        { src: require("@/assets/Marcas/venier.jpg"), alt: "Venier" },
        { src: require("@/assets/Marcas/wd80.jpg"), alt: "WD-80" },
      ],
    };
  },
  computed: {
    groupedImages() {
      const groupSize = this.isMobile ? 1 : 4;
      return this.imagenes.reduce((acc, curr, i) => {
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

<style>

</style>
    
<style scoped>
#prodcutos {
    background-color: #f2f2f2 !important;
}
.carousel {
  width: 100% !important;
}
.carousel-item {
  min-height: 200px;
}
.carousel-caption {
  justify-content: center !important ;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}

.custom-btn {
    padding: 0.75rem 1.5rem;
  font-size: 1.1rem;
  font-weight: bold;
  color: #8b2d19; /* Rojo óxido */
  background-color: transparent;
  border: 2px solid #8b2d19; /* Borde óxido */
  border-radius: 8px;
  transition: all 0.3s ease;
  text-transform: uppercase;
}

.custom-btn:hover {
    background-color: #8b2d19; /* Fondo óxido al hacer hover */
  color: #fff; /* Texto blanco */
  border-color: #8b2d19;
}
/* 
.custom-carrousel, .carousel-item, .carousel-item.active, .carousel-inner{
    max-height: 200px !important;
} */



@media (max-width: 576px) {
  .container-fluid {
    background-size: auto;
  }
}
</style>
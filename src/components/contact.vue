<template>
  <div id="contacto" class="contacto pt-4">
    <b-container class="pt-5 pb-5">
      <h1 class="text-center pb-5 font-weight-bold">Contacto</h1>
      <b-row>
        <b-col md="6" class="col-map pt-4" sm="12">
          <p class="mb-0">
            <i class="bi bi-geo-alt-fill"></i> Gral. Gervasio Artigas 3985, Agronomía, Capital Federal.
          </p>       
          <p class="mb-0"><i class="bi bi-telephone"></i> 011 4573-1263</p>
          <p class="text-nowrap mb-0">
            <i class="bi bi-envelope"></i> ferreteriatardini@gmail.com
          </p>          
          <div class="map">
            <iframe
              src="https://maps.google.com/maps?q=ferreteria%20tardini&t=&z=17&ie=UTF8&iwloc=&output=embed"
              width="550"
              height="550"
              style="border: 0"
              allowfullscreen=""
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
            ></iframe>
          </div>
        </b-col>
        <b-col md="6" sm="12">
          <contactForm />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import contactForm from "./contactForm.vue";

export default {
  name: "contact",
  components: { contactForm },
  data() {
    return {
      form: {
        nombre: "",
        apellido: "",
        email: "",
        consulta: "",
      },
      isDesktop: window.innerWidth >= 992,
    };
  },
  methods: {
    onSubmit() {
      var hola = "";
      return hola;
    },
  },
};
</script>
<style>
/* Contenedor del iframe */
.map {
  position: relative;
  padding-bottom: 56.25%; /* Relación de aspecto 16:9 */
  height: 0;
  overflow: hidden;
  max-width: 100%;
  background: #eee;
}

/* iframe dentro del contenedor */
.map iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 0;
}

/* iconos */
.bi-geo-alt-fill::before {
  vertical-align: text-top !important;
}

.col-map {
  border-right: solid;
  border-color: #ededed;  
}

.contacto {
  background-color: #f2f2f2;
}

.col-map a {
  color: #C0392B  !important;
}

.border {
  border: var(--bs-border-width) var(--bs-border-style) var(--bs-border-color) !important;
  border-radius: 7px !important;
  /* background-color: white; */
}

.contact-btn {
  background-color: #006b93 !important;
  border-color: #006b93 !important;
}

@media (max-width: 576px) {
  h1 {
    text-align: center !important;
  }
}
</style>
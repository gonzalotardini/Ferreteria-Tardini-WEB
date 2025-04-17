<template>
  <section class="hero-section d-flex align-items-center justify-content-center text-center">
    <div class="overlay w-100 h-100 d-flex flex-column align-items-center justify-content-center">
      <h1>FERRETERÍA TARDINI HNOS.</h1>
      <b-btn href="#contacto" class="mt-4 custom-btn"><i class="bi bi-envelope-fill mr-2"></i> CONTACTANOS</b-btn>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped>
.hero-section {
  background-image: url('@/assets/tools.jpeg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  height: 80vh; /* altura inicial grande */
  position: relative;
}

.overlay {
  background-color: rgba(0, 0, 0, 0.5); /* oscurece la imagen para mejorar legibilidad */
  color: #F8F9F9;
  padding: 2rem;
}

h1 {
  font-size: 75px;
  color: #F8F9F9;
  font-weight: 500 !important;
}

.custom-btn {
  background-color: #A93226; /* rojo óxido */
  color: #fff;
  border: none;
  font-weight: bold;
  letter-spacing: 1px;
  padding: 12px 28px;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-size: 16px;
}

.custom-btn:hover {
  background-color: #922B21;
  transform: scale(1.05);
}


/* Responsive: ajusta altura e imagen en pantallas chicas */
@media (max-width: 768px) {
  .hero-section {
    height: 50vh;
  }
  h1 {
    font-size: 40px;
  }
}

@media (max-width: 576px) {
  .hero-section {
    height: 40vh;
  }
  h1 {
    font-size: 30px;
  }
}
</style>
<template>
    <div>
      <inicio/>
      <nosotros/>
      <productos/>
      <clientes/>
      <conctact/>
      <foot/>
    </div>
  </template>
  
  <script>
import inicio from '../components/inicio.vue';
import nosotros from '../components/nosotros.vue';
import productos from '../components/productos.vue'
import conctact from '../components/contact.vue';
import clientes from '../components/clientes.vue';
import foot from '../components/foot.vue';

  export default {
    name: 'Home',
    components:{
    inicio,
    nosotros,
    productos,
    conctact,
    foot,
    clientes
    }
  };
  </script>
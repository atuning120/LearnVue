<script setup>
import {ref, reactive, onMounted} from 'vue';
import {db} from '../data/guitarras.js';

  const guitarras=ref([]);
  

  onMounted(() => {
    guitarras.value=db;
  });
</script>

<template>
    <div class="row mt-5">


      <div v-for="guitarra in guitarras" class="col-md-6 col-lg-4 my-4 row align-items-center">
        <div class="col-4">
          <img class="img-fluid" :src="guitarra.imagen" alt="imagen guitarra">
        </div>

        <div class="col-8">
          <h3 class="text-black fs-4 fw-bold text-uppercase">{{ guitarra.nombre }}</h3>
          <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit quae labore odit magnam in autem nesciunt,
            amet deserunt</p>
          <p class="fw-black text-primary fs-3">${{ guitarra.precio }}</p>
          <button type="button" class="btn btn-dark w-100 ">Agregar al Carrito</button>
        </div>
      </div><!-- FIN GUITARRA -->

    </div>
</template>

<style scoped lang="scss">

</style>
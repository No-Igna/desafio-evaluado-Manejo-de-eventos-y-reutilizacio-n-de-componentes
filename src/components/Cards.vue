<template>
  <div v-if="citas.length" class="container">
    <h2>Citas Registradas</h2>
    <div class="row justify-content-start">
      <div class="col-3 p-2" v-for="(cita, index) in citas" :key="index">
        <div class="card text-center" :class="cita.gravedad">
          <div class="card-body">
            <h5 class="card-title">Paciente:</h5>
            <p class="card-text">{{ cita.paciente }}</p>
            <hr>
            <h5 class="card-title">Fecha:</h5>
            <p class="card-text">{{ cita.fecha }}</p>
            <hr>
            <h5 class="card-title">Hora:</h5>
            <p class="card-text">{{ cita.hora }}</p>
            <hr>
            <h5 class="card-title">Motivo:</h5>
            <p class="card-text">{{ cita.motivo }}</p>
            <hr>
            <button type="button" class="btn btn-secondary my-1" @click="eliminarCita(index)">Eliminar Cita</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cards',
  props: {
    citas: Array,
  },
  data() {
    return {};
  },
  methods: {
    eliminarCita(index) {
      this.$emit('eliminar-cita', index);
    }
  }
};
</script>

<style scoped>
.baja {
  background-color: green;
  color: white;
}

.media {
  background-color: yellow;
}

.alta {
  background-color: red;
  color: white;
}
</style>
<template>
  <div class="container my-3 formulario">
    <h1>Administrador de citas medicas</h1>
    <form class="row" @submit.prevent="submitForm">
      <div class="mt-3 col-2">
        <label for="paciente" class="form-label" :style="{ color: form.paciente ? 'black' : 'red' }">Paciente:</label>
        <input type="text" class="form-control" v-model="form.paciente" id="paciente" required />
      </div>
      <div class="mt-3 col-2">
        <label for="fecha" class="form-label" :style="{ color: form.fecha ? 'black' : 'red' }">Fecha:</label>
        <input type="date" class="form-control" v-model="form.fecha" id="fecha" required />
      </div>
      <div class="mt-3 col-2">
        <label for="hora" class="form-label" :style="{ color: form.hora ? 'black' : 'red' }">Hora:</label>
        <input type="time" class="form-control" v-model="form.hora" id="hora" required />
      </div>
      <div class="mt-3 col-2">
        <label for="gravedad" class="form-label" :style="{ color: form.gravedad ? 'black' : 'red' }">Gravedad:</label>
        <select class="form-control" v-model="form.gravedad" id="gravedad" required>
          <option value="" disabled selected>Seleccione la gravedad</option>
          <option value="baja">Baja</option>
          <option value="media">Media</option>
          <option value="alta">Alta</option>
        </select>
      </div>
      <div class="mt-3 col-4">
        <label for="motivo" class="form-label" :style="{ color: form.motivo ? 'black' : 'red' }">Motivo:</label>
        <textarea class="form-control" v-model="form.motivo" id="motivo" required></textarea>
      </div>
      <button type="submit" class="btn btn-primary mt-3">Agregar</button>
    </form>
  </div>
</template>
 
<script>
export default {
  name: 'Formulario',
  data() {
    return {
      form: {
        paciente: "",
        fecha: "",
        hora: "",
        gravedad: "",
        motivo: ""
      },
    };
  },
  methods:{
    submitForm(){
      //submit-form con los datos del formulario
      this.$emit('submit-form', this.form);
      //reset del formulario
      this.form={
        paciente: "",
        fecha: "",
        hora: "",
        gravedad: "",
        motivo: ""
      }
    }
  }
};
</script>

<style scoped>
.formulario {
  padding: 1rem;
  border: 1px solid #2f2f2f;
  border-radius: 10px;
}
.empty-label{
  color: red;
}
</style>
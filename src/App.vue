<script>
import Formulario from './components/Formulario.vue';
import Cards from './components/Cards.vue';
 
export default{
  components:{
    Formulario, Cards
  },
  data(){
    return{
      citas:[],
    };
  },
  methods:{
    agregarCitas(datosFormulario){
      this.citas.push(datosFormulario);
    },
    eliminarCitas(index){
      this.citas.splice(index,1);
    }
  }
}
</script>

<template>
  <Formulario @submit-form="agregarCitas"/>
  <Cards :citas="citas" @eliminar-cita="eliminarCitas"/>
</template>

<style scoped>

</style>

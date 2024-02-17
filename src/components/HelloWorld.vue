<template>
  <v-card class="card">
    <v-form class="form">
      <v-col cols="11">
        <h1 class="titulo">RIESGOS</h1>
        <v-text-field
          label="Nombre del riesgo"
          v-model="datosRiesgo.nombre"
        ></v-text-field>
        <v-select label="Dependencia" :items="items"></v-select>
        <textarea
          class="textarea"
          placeholder="Descripcion"
          v-model="datosRiesgo.descripcion"
        ></textarea>
        <v-btn class="btn">Guardar</v-btn>
      </v-col>
    </v-form>
  </v-card>

  <v-card class="card">
    <v-form class="form">
      <v-col cols="11">
        <h1 class="titulo">CAUSA</h1>
        <v-text-field
          label="nombre causa"
          v-model="datosCausa.nombre"
        ></v-text-field>
        <v-select label="Riesgo" :items="riesgos"></v-select>
        <textarea
          class="textarea"
          placeholder="Descripcion"
          v-model="datosCausa.descripcion"
        ></textarea>
        <v-btn class="btn">Guardar</v-btn>
      </v-col>
    </v-form>
  </v-card>
  <v-card class="card">
    <v-form class="form">
      <v-col cols="11">
        <h1 class="titulo">DEPENDENCIAS</h1>
        <v-text-field label="nombre dependencia"></v-text-field>
        <v-btn class="btn">Guardar</v-btn>
      </v-col>
    </v-form>
  </v-card>
</template>
<style>
.card {
  text-align: center;
  width: 500px;
  height: 600px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #c7c8c8;
}
.form {
  width: 500px;
  height: 600px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.textarea {
  width: 440px;
  height: 200px;
}
.btn {
  top: 30px;
}
</style>
<script>
import axios from 'axios';

export default {
  name: "HelloWorld",

  data: () => ({
    select: null,
    items: ["Coordinador de formacion", "Coordinador academico", "Lider ficha"],
    riesgos: ["riesgos"],

    datosRiesgo: {
      nombre: "",
      descripcion: "",
      dependencia: "",
    },
    datosCausa: {
      nombre: "",
      descripcion: "",
      riesgo: "",
    },
  }),
  mounted() {
    axios.get("http://localhost:3000/Riesgo").then(response =>{
      console.log(response.data),
    }).catch(error =>{
      console.log(error)
    })

  }
};
</script>

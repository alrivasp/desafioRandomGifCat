<template>
  <div class="container">
    <div class="container__form">
      <div class="container__base">
        <div class="label__titulo">
          <label class="container__space" for="input_title">Titulo:</label>
          <br />
          <br />
          <label for="selected_filter">Filtro:</label>
          <br />
          <br />
          <label for="selected_color">Color:</label>
          <br />
          <br />
          <label for="input_size">Tamaño:</label>
        </div>
        <div style="text-align: left;">
          <input v-model="title" type="text" id="input_title"/>
          <br />
          <br />
          <select id="selected_filter" v-model="filterSelected">
            <option value="">Selecccionar</option>
            <option v-for="filter in filters" :key="filter">{{ filter }}</option>
          </select>
          <br />
          <br />
          <select id="selected_color" v-model="colorSelected">
            <option value="">Selecccionar</option>
            <option v-for="color in colors" :key="color" :value="color.english">
              {{ color.spanish }} 
            </option>
          </select>
          <div class="circulo" :style="{'background-color': this.colorSelected}"></div>
          <br />
          <br />
          <input v-model="size" type="number" id="input_size" />
        </div>
      </div>
    </div>
    <div class="container__button">
      <button @click="fetchApiCat">Obtener mi gatito</button>
      <div>
        <img v-if="photo" :src="photo" alt="foto gato">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      error: '',
      photo: '',
      title: '',
      size: 0,  
      filterSelected: "",
      filters: ["blur", "mono", "sepia", "negative", "paint", "pixel"],
      colorSelected: "",
      colors: [
        { english: "red", spanish: "Rojo" },
        { english: "blue", spanish: "Azul" },
        { english: "green", spanish: "Verde" },
        { english: "white", spanish: "Blanco" },
        { english: "yellow", spanish: "Amarillo" },
      ],
    };
  },
  methods:{
    fetchApiCat(){
      this.photo = `https://cataas.com/cat/gif/says/${this.title}?filter=${this.filterSelected}&color=${this.colorSelected}&size=${this.size}&type=or`
    },
  }
};
</script>

<style scoped>
.container {
  text-align: center;
}
.container__form {
  text-align: center;
}
.container__base{
  padding-top: 30px;
  padding-bottom: 30px;
  text-align: center;
  width: 100%;
  background-color: #b46b6b;
  display: inline-flex;
}
.label__titulo{
  width: 48%;
  text-align: right;
}
.circulo{
  display: inline-block;
  margin-left: 20px;
  width: 15px;
  height: 15px;
  -moz-border-radius: 50%;
  -webkit-border-radius: 50%;
  border-radius: 50%;      
}
.container__button{
  padding: 30px;
}
</style>
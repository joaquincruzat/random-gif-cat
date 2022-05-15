<template>
  <section>
    <h1 class="title">Random Cat Gif Generator</h1>
    <form class="form-cat" action="" v-on:submit.prevent="gifGenerator()">
      <div class="input-cat">
        <label for="">Título: </label>
        <input type="text" placeholder="ingrese el texto de la imagen" v-model="titleCat" required/>
      </div>
      <div class="filter-cat">
        <label for="filter">Filtro: </label>
        <select name="filter" id="" v-model="filterCat" required>
          <option value="" selected disabled>selecciona filtro</option>
          <option value="mono">monocromático</option>
          <option value="blur">blur</option>
          <option value="sepia">sepia</option>
          <option value="negative">negativo</option>
          <option value="pixel">pixel</option>
          <option value="paint">paint</option>
        </select>
      </div>
      <div class="color-cat">
        <label for="color">Color de texto: </label>
        <select name="color" id="" v-model="colorCat" required>
           <option value="" selected disabled>elije color</option>
          <option value="green">verde</option>
          <option value="red">rojo</option>
          <option value="blue">azul</option>
          <option value="yellow">amarillo</option>
          <option value="black">negro</option>
          <option value="white">blanco</option>
        </select>
        <div class="color-cat-circle" :style="{backgroundColor: this.colorCat}"></div>
      </div>
      <div class="size-cat">
        <label for="size">Tamaño: </label>
        <input type="number" name="size" placeholder="ingrese tamaño letra" v-model="sizeCat" required>
      </div>
      <button type="submit" class="button-cat">Obtener mi gatito</button>
          <div>
    </div>
    </form>
         <div>
           <img class="gif-cat" :src="url" alt="">
         </div>
  </section>
</template>

<script>

export default {
  name: "App",
  data: () => {
    return {
    titleCat:"",
    filterCat:"",
    colorCat:"",
    sizeCat:"",
    url:"",
    }
  },
  methods: {
    gifGenerator () {
      this.url = `https://cataas.com/cat/gif/says/${this.titleCat}?filter=${this.filterCat}&color=${this.colorCat}&size=${this.sizeCat}&width=500&height=300`;
  }
}
};

</script>

<style>
* {
  margin: 0;
  padding: 0;
}
body {
  background-color: azure;
  font-family: 'Lucida Sans';
  text-align: center;
}
.title {
  font-size: 3rem;
  margin-top: 30px;
  margin-bottom: 50px;
}
.form-cat{
  background-color: pink;
  padding: 30px;
  justify-content: center;
}
.input-cat, .size-cat , .color-cat, .button-cat, .filter-cat{
  margin-bottom: 15px;
}
.color-cat{
  display: flex;
  gap: 5px;
  justify-content: center;
}
.button-cat{
  padding: 5px;
}
.gif-cat{
  margin-top: 30px;
}
.color-cat-circle{
  border-radius: 50%;
  width: 25px;
  height: 25px;
  margin-left: 5px;
}

</style>
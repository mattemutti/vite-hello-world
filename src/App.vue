<script>
export default {
  data() {
    return {
      message: 'Hello Vue',
      genMessage: null,
      numbers: []
    }
  },
  methods: {
    generateMessage() {
      // axios.get('https://flynn.boolean.careers/exercises/api/random/name')
      //   .then((response) => {
      //     console.log(response);
      //   })
      this.genMessage = Math.round(Math.random() * 100 + 1);
      this.numbers.push(this.genMessage);
      console.log(this.genMessage);
      console.log(this.numbers);

    }
  },
  mounted() {
    console.log(this.message);
    console.log(this.genMessage);
  }


}
</script>


<!-- ****** html ************************************************************** *** -->

<template>
  <h1>{{ message }}</h1>
  <div>
    <button @click="generateMessage">Genera</button>
  </div>
  <div id="number" v-if="genMessage != null">{{ genMessage }}</div>
  <div v-for="number in numbers">{{ number }}</div>
</template>


<!-- ****** css ************************************************************** *** -->

<style>
body {
  background-color: red;
  text-align: center;

  h1 {
    text-align: center;
    color: white;
  }

  button {
    text-align: center;
    background-color: white;
    color: red;
    font-size: 50px;
  }

  #number {
    font-size: 100px;
    color: green;
  }

}
</style>
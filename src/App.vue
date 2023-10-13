<script>
export default {
  data() {
    return {
      titel: 'Vue-Basisfunctionaliteiten',
      intro: 'Dit is een voorbeeldomschrijving',
      naam: 'Lennie Mouton',
      leeftijd: '19',
      website: 'https://devtools.vuejs.org/',
      afbeelding: './assets/bladeren.jpg',

      number: 0
    }
  },
  methods: {
    randomTekst() {
      let randomNumber = math.random(0,1);
      if (randomNumber < 0.5) {
        return "Testjeeee"
      } else {
        return "Wie zoekt die vindt! - " + this.titel;
      }
    },
      addnumber() {
        this.number = this.number + 2;
      },
      randomGetal() {
        return Math.random(0,1);
      }
    }
}
</script>

<template>
  <h1>Welkom in de {{titel}}</h1>
  <p>{{ intro }}</p>

  <label v-bind:for="naam">{{ naam }}</label>
  <input type="text" v-bind:name="naam" v-bind:id="naam">
  <!-- <input type="text" v-bind:name="naam" :id="naam"> -->

  <img v-bind:src="afbeelding" alt="Bladeren">

  <p>{{ number }}</p>
  <button v-on:click="addnumber()">Count</button>
  <!-- <button @click="number++">Count</button> -->

  <div>
    <h2>{{ naam }}</h2>
    <p> leeftijd: {{ leeftijd }} jaar!</p>
    <p>{{ randomGetal() }}</p>
    <a :href="website">Vue website</a>
  </div>



  <!-- <label for="product">Product</label>
  <input type="text" name="product" id="product" v-model="product">
  <button ></button> -->
</template>

<style>
img {
  width: 75%;
}
</style>

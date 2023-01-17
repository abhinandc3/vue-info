<template>
  <div id="app">
    <section id="assignment">
      <!-- 1) Output your name -->
      <h2>Name:{{ name }}</h2>
      <!-- 2) Output your age -->
      <p>{{ age }}</p>
      <!-- 3) Output your age + 5 -->
      <p>{{ ageF() }}</p>
      <!-- 4) Output a random number (0 to 1) -->
      <p>Favorite Number: RANDOM NUMBER BETWEEN 0 AND 1 {{randomNumber()}}</p>
      <div>
        <!-- 5) Display some image you found via Google -->
        <img v-bind:src=img />
      </div>
      <!-- 6) Prepopulate the input field with your name via the "value" attribute -->
      <input type="text" v-bind:value="name" />
    </section>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';

export default {
  data() {
    return {
      name: 'myname',
      age: '22',
      img :'data:image/jpeg;base64,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'
    };
  },

  methods: {
    ageF() {
      return this.age + 5;
    },
    randomNumber() {
      return Math.random();
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
* {
  box-sizing: border-box;
}

html {
  font-family: 'Jost', sans-serif;
}

body {
  margin: 0;
}

section {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
}

h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #970076;
  margin: 0 0 1rem 0;
}

p {
  font-size: 1.25rem;
  font-weight: bold;
  background-color: #970076;
  padding: 0.5rem;
  color: white;
  border-radius: 25px;
}

input {
  font: inherit;
  border: 1px solid #ccc;
}

input:focus {
  outline: none;
  border-color: #1b995e;
  background-color: #d7fdeb;
}

button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}

button:hover,
button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
</style>

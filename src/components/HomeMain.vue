<script lang="ts">
import axios from 'axios'

export default {
  data() {
    return {
      joke: '',
      answer: ''
    }
  },
  methods: {
    async getRandomJoke() {
      try {
        const response = await axios.get('https://carambar-api-eq5f.onrender.com/api/blagues/random')
        this.joke = response.data.joke
        this.answer = response.data.answer
      } catch (error) {
        console.error(error)
      }
    }
  }
}
</script>

<template>
  <main>
    <button type="button" @click="getRandomJoke" class="btn-logo">
      <img src="../assets/images/logo.png" alt="logo" class="img-logo" />
    </button>
    <div class="joke-block">
      <p class="joke">{{ joke }}</p>
      <p class="answer">{{ answer }}</p>
    </div>
  </main>
</template>

<style scoped>
main {
  width: 100%;
  height: 100%;
  padding: 4rem 0;
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: center;
  gap: 4rem;
}

.btn-logo {
  background-color: transparent;
  border-radius: 48%;
  box-shadow: 0 5px 5px black;
  width: 290px;
  height: auto;
  cursor: pointer;
}

.btn-logo:hover {
  transform: scale(1.1);
  background-color: #ffee00;
}

.img-logo {
  width: 100%;
  height: auto;
}

.joke-block {
  height: 35vh;
  width: 800px;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  padding: 1rem 1rem;
  border: 1px solid black;
  border-radius: 30px 30px;
  background-color: #ffee00;
  font-size: 1.5rem;
  letter-spacing: 2px;
}

.joke {
  text-align: center;
  font-style: italic;
  color: #2c3e50;
}

.answer {
  text-align: center;
  color: darkslategrey;
}

@media (max-width: 768px) {
  main {
    padding: 2rem 0;
  }

  .joke-block {
    width: 95vw;
    height: 30vh;
    font-size: 1rem;
  }
}
</style>

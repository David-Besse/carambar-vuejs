<template>
  <header>
    <h1>Bienvenue sur Blagues Carambar !</h1>
    <p>cliquez sur le logo pour faire apparaître une blague</p>
  </header>
</template>

<style scoped>
header {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 2rem 2rem;
  gap: 2rem;
  letter-spacing: 1px;
}

header h1 {
  text-align: center;
  font-size: 2.4rem;
  font-weight: 400;
  color: #2c3e50;
}

header p {
  text-align: center;
  font-size: 1.2rem;
  color: gray;
  font-style: italic;
}

@media (max-width: 768px) {
  header h1 {
    font-size: 1.6rem;
    text-wrap: wrap;
  }

  header p {
    font-size: 1rem;
    text-wrap: wrap;
    padding: 0 1rem;
  }
}
</style>

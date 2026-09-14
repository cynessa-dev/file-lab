<script setup lang="ts"></script>

<template>
  <main>
    <section id="hero">
      <h1>FileLab Tagline goes here, can't think of anything just yet.</h1>
      <p>
        FileLab brief introduction goes here, it should be clear and concise to explain what the
        service does.
      </p>
    </section>
  </main>
</template>

<style scoped>
section {
  position: relative;
  display: flex;
  flex-direction: column;
}

h1 {
  margin: auto 0;
  max-width: 100vw;
  text-align: center;
}

p {
  position: absolute;
  bottom: 0;
  max-width: 15rem;
}

@media (min-width: 720px) {
  h1 {
    max-width: 40vw;
    text-align: left;
  }

  p {
    max-width: 20rem;
  }
}
</style>

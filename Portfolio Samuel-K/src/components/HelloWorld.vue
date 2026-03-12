<script setup lang="ts">
defineProps<{
  msg: string
}>()
</script>

<template>
  <div class="greetings" id="home">
    <h1 class="white hero-title">{{ msg }}</h1>
    <h3 class="hero-subtitle">
      Samuel Kappel : Bachelor en informatique de Gestion
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  margin: 0 auto;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

.hero-title {
  animation: hero-fade-up 0.6s ease both;
}

.hero-subtitle {
  animation: hero-fade-up 0.6s ease 0.15s both;
}

@keyframes hero-fade-up {
  from {
    opacity: 0;
    transform: translateY(14px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>

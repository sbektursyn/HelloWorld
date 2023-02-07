<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h3>
      Privet ya Sagyndyk
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
  </div>
  <table>
    <tbody>
      <tr>
        <td>first</td>
        <td>buy a car</td>
      </tr>
      <tr>
        <td>second</td>
        <td>write a code</td>
      </tr>
      <tr>
        <td>third</td>
        <td>wake up at 8</td>
      </tr>
    </tbody>
  </table>
</template>

<style scoped>
table{border:1px solid #000; color:#a88;}
td{border:1px solid #000;}


h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>

<template>
  <div id="app">
    <header>
      <h1>{{ title }}</h1>
    </header>

    <main>
      <p>Welcome to your Vue 2 template app 🎉</p>
      <input v-model="message" placeholder="Type something..." />
      <p>You typed: {{ message }}</p>
    </main>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      title: "Vue 2 Template App",
      message: "",
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  padding: 2rem;
}

header {
  background: #42b983;
  color: white;
  padding: 1rem;
  border-radius: 8px;
}
</style>

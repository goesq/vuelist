<template>
  <div id="app">
    <h1>Exercícios Vue.js</h1>

    <!-- Exercício 1: Exibir uma Mensagem -->
    <section>
      <h2>1. Exibir uma Mensagem</h2>
      <p>{{ mensagem }}</p>
    </section>

    <!-- Exercício 2: Contador de Cliques -->
    <section>
      <h2>2. Contador de Cliques</h2>
      <button @click="incrementar">Clique aqui</button>
      <p>Contador: {{ contador }}</p>
    </section>

    <!-- Exercício 3: Mostrar/Ocultar Texto -->
    <section>
      <h2>3. Mostrar/Ocultar Texto</h2>
      <button @click="toggleMostrar">
        {{ mostrar ? "Ocultar" : "Mostrar" }} Texto
      </button>
      <p v-if="mostrar">Este é o texto que pode ser mostrado ou ocultado.</p>
    </section>

    <!-- Exercício 4: Lista de Itens com v-for -->
    <section>
      <h2>4. Lista de Itens com v-for</h2>
      <ul>
        <li v-for="(item, index) in itens" :key="index">{{ item }}</li>
      </ul>
    </section>

    <!-- Exercício 5: Entrada de Texto com v-model -->
    <section>
      <h2>5. Entrada de Texto com v-model</h2>
      <input type="text" v-model="nome" placeholder="Digite seu nome" />
      <p>Você digitou: {{ nome }}</p>
    </section>

    <!-- Exercício 6: Alterar Estilo com Scoped CSS -->
    <section>
      <h2>6. Alterar Estilo com Scoped CSS</h2>
      <p class="texto-verde">Este texto está estilizado com Scoped CSS!</p>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Exercício 1
      mensagem: "Bem-vindo ao Vue.js!",

      // Exercício 2
      contador: 0,

      // Exercício 3
      mostrar: false,

      // Exercício 4
      itens: ["Item 1", "Item 2", "Item 3", "Item 4"],

      // Exercício 5
      nome: "",
    };
  },
  methods: {
    // Exercício 2
    incrementar() {
      this.contador++;
    },
    // Exercício 3
    toggleMostrar() {
      this.mostrar = !this.mostrar;
    },
  },
};
</script>

<style scoped>
/* Exercício 6 */
.texto-verde {
  color: green;
  font-weight: bold;
}
</style>

<style>
/* Estilo geral opcional */
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f9f9f9;
  color: #333;
}

#app {
  max-width: 600px;
  margin: 20px auto;
  padding: 20px;
  background: white;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

section {
  margin-bottom: 20px;
}

button {
  margin-top: 10px;
  padding: 10px 15px;
  border: none;
  background-color: #42b983;
  color: white;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #359a6e;
}
</style>

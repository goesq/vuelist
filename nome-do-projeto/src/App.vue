<template>
  <div id="app">
    <h1>Exercícios Práticos</h1>

    <!-- Exercicio 1: Contador de Cliques -->
    <section>
      <h2>1. Contador de Cliques</h2>
      <p>Contador: {{ contador }}</p>
      <button @click="incrementar">Incrementar</button>
      <button @click="decrementar">Decrementar</button>
    </section>

    <!-- Exercicio 2: Mostrar/Ocultar Texto -->
    <section>
      <h2>2. Mostrar/Ocultar Texto</h2>
      <button @click="toggleTexto">
        {{ textoVisivel ? "Ocultar" : "Mostrar" }} Texto
      </button>
      <p v-if="textoVisivel">Este é o texto que pode ser mostrado ou ocultado.</p>
    </section>

    <!-- Exercicio 3: Lista Dinâmica -->
    <section>
      <h2>3. Lista Dinâmica</h2>
      <input
        type="text"
        v-model="novoItem"
        placeholder="Adicione um item"
        @keyup.enter="adicionarItem"
      />
      <button @click="adicionarItem">Adicionar</button>
      <ul>
        <li v-for="(item, index) in lista" :key="index" @click="removerItem(index)">
          {{ item }}
        </li>
      </ul>
    </section>

    <!-- Exercicio 4: Input de Nome -->
    <section>
      <h2>4. Input de Nome</h2>
      <input
        type="text"
        v-model="nome"
        placeholder="Digite seu nome"
      />
      <p v-if="nome">Bem-vindo, {{ nome }}!</p>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Exercício 1
      contador: 0,

      // Exercício 2
      textoVisivel: false,

      // Exercício 3
      novoItem: "",
      lista: [],

      // Exercício 4
      nome: "",
    };
  },
  methods: {
    // Exercício 1
    incrementar() {
      this.contador++;
    },
    decrementar() {
      this.contador--;
    },

    // Exercício 2
    toggleTexto() {
      this.textoVisivel = !this.textoVisivel;
    },

    // Exercício 3
    adicionarItem() {
      if (this.novoItem.trim() !== "") {
        this.lista.push(this.novoItem.trim());
        this.novoItem = "";
      }
    },
    removerItem(index) {
      this.lista.splice(index, 1);
    },
  },
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

section {
  margin-bottom: 20px;
}

button {
  margin: 5px;
  padding: 10px;
  background-color: #42b983;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #359a6e;
}

input {
  padding: 10px;
  margin: 5px 0;
  width: 100%;
  box-sizing: border-box;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  background: #f3f3f3;
  margin: 5px 0;
  padding: 10px;
  border-radius: 5px;
  cursor: pointer;
}

li:hover {
  background: #ddd;
}
</style>

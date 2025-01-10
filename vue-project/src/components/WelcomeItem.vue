<template>
  <div class="form-container">
    <h2>Cadastro</h2>
    <form @submit.prevent="handleSubmit">
      <div>
        <input type="text" v-model="user.name" placeholder="Nome" required />
      </div>
      <div>
        <input type="email" v-model="user.email" placeholder="Email" required />
      </div>
      <div>
        <input type="password" v-model="user.password" placeholder="Senha" required />
      </div>
      <button type="submit">Cadastrar</button>
    </form>
    <div v-if="submitted" class="success-message">
      <p>Cadastro realizado com sucesso!</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const user = ref({
  name: '',
  email: '',
  password: ''
})

const submitted = ref(false)

const handleSubmit = () => {
  if (user.value.name && user.value.email && user.value.password) {
    submitted.value = true
    console.log('Dados do usuário:', user.value)
  }
}
</script>

<style scoped>
body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f9;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

.form-container {
  background: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  width: 300px;
}

.form-container h2 {
  text-align: center;
  margin-bottom: 20px;
}

.form-container input {
  width: 100%;
  padding: 8px;
  margin: 8px 0;
  border-radius: 4px;
  border: 1px solid #ccc;
}

.form-container button {
  width: 100%;
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
}

.form-container button:hover {
  background-color: #45a049;
}

.success-message {
  color: green;
  text-align: center;
  margin-top: 20px;
}
</style>

<script setup>

import {ref} from "vue";

let user = ref({
  name: '',
  email: '',
  password: '',
})

const registeruser = () => {
  axios.post(
      route("manager.store"),
      user.value
  ).then(({ data }) => {

  }).catch((err) => {

  });
}
</script>

<template>
  <div class="p-12">
    <div>
    </div>
    <div class="max-w-md mx-auto border shadow p-4 rounded-lg">
      <form class="grid grid-cols-1 gap-4">
        <div class="grid grid-cols-1 space-y-1">
          <label for="">Correo electronico</label>
          <input v-model="user.email" type="email" class="border rounded">
        </div>

        <div class="grid grid-cols-1 space-y-1">
          <label for="">Nombre completo</label>
          <input v-model="user.name" type="text" class="border rounded">
        </div>

        <div class="grid grid-cols-1 space-y-1">
          <label for="">Contraseña</label>
          <input v-model="user.password" type="password" class="border rounded">
        </div>

        <template v-if="![user.password, user.name, user.email].includes('')">
          <button type="button" @click="registeruser" class="p-2 shadow rounded bg-indigo-500 text-white hover:bg-indigo-700 transition">
            Registrarme
          </button>

        </template>
      </form>
    </div>
  </div>
</template>

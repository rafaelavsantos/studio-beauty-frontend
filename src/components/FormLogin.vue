<template>
  <div class="q-ma-lg">
    <q-form @submit.prevent.stop="onSubmit()">
      <div class="row justify-center q-mb-md">
        <img src="../assets/svg/logo.svg" alt="Logo">
      </div>

      <q-input filled label="E-mail" class="q-mt-md">
        <template v-slot:append>
          <q-icon name="mail" color="primary" />
        </template>
      </q-input>

      <q-input filled label="Password" class="q-mt-md">
        <template v-slot:append>
          <q-icon name="lock" color="primary" />
        </template>
      </q-input>

      <div class="q-mt-md">
        <q-btn label="Login" type="submit" color="primary" class="full-width" />
      </div>
    </q-form>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router';


const router = useRouter();

async function onSubmit() {
  router.push("/dashboard")

  console.log("Cheguei aqui")
}
</script>
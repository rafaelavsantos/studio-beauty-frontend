<template>
  <q-layout view="hHh lpR fFf">
    <div class="row items-center">
      <q-page-container class="col-4">
        <router-view />
      </q-page-container>

      <div class="container-img-login col-8 row items-center justify-center">
        <q-img src="../assets/svg/illustration.svg" alt="" class="col" style="width: 400px; max-width: 75%" />
      </div>
    </div>
  </q-layout>
</template>

<script setup>
</script>

<style scoped>
.container-img-login {
  flex: 1;
  height: 100vh;
  background-color: rgba(241, 118, 139, 0.267);
}
</style>

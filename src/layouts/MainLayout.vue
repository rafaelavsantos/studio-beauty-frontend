<template>
  <q-layout view="lhr lpR lFr">
    <q-header elevated>
      <q-toolbar>
        <q-btn flat dense round icon="menu" aria-label="Menu" @click="toggleLeftDrawer" />

        <q-toolbar-title>
          Sistema de Gerenciamento para Salão de Beleza
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered class="bg-pink-1" :mini="miniState"
      @mouseover="miniState = false" @mouseout="miniState = true" :width="200" :breakpoint="500">
      <q-list>
        <q-item-label header>
          SGSB
        </q-item-label>

        <EssentialLink v-for="link in linksList" :key="link.title" v-bind="link" />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer class="bg-black row items-center justify-center q-pa-xs">
      <p>Desenvolvido por Rafaela &copy; 2024</p>
    </q-footer>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const leftDrawerOpen = ref(false);
const miniState = ref(false);

const linksList = [
  {
    title: 'Dashboard',
    icon: 'dashboard',
    link: '/teste'
  },
  {
    title: 'Usuários',
    icon: 'person',
    link: '/teste'
  },
  {
    title: 'Administradores',
    icon: 'supervisor_account',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Funcionários',
    icon: 'groups',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Clientes',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Serviços',
    icon: 'settings',
    link: 'https://twitter.quasar.dev'
  }
]

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}

</script>

<style scoped>
p {
  margin: 0;
}
</style>

<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import { ref } from 'vue'

const rail = ref(true)
const drawer = ref(true)
</script>

<template>
  <v-layout>
    <!-- Footer -->
    <v-footer app border>footer</v-footer>

    <!-- Navbar -->
    <v-navigation-drawer v-model="drawer" :rail="rail" @click="rail = false">
      <v-list-item
        prepend-avatar="https://randomuser.me/api/portraits/men/85.jpg"
        title="John Leider"
        nav
      >
        <template v-slot:append>
          <v-btn variant="text" icon="mdi-chevron-left" @click.stop="rail = !rail"></v-btn>
        </template>
      </v-list-item>

      <v-divider></v-divider>

      <v-list density="compact" nav>
        <v-list-item prepend-icon="mdi-home-city" title="Home" value="home"></v-list-item>
        <v-list-item prepend-icon="mdi-account" title="My Account" value="account"></v-list-item>
        <v-list-item
          prepend-icon="mdi-account-group-outline"
          title="Users"
          value="users"
        ></v-list-item>
      </v-list>
    </v-navigation-drawer>

    <!-- Appbar -->
    <v-app-bar :elevation="1" title="PNP - Dupa Saraswati 108" density="">
      <template v-slot:prepend>
        <v-app-bar-nav-icon @click="rail = false"></v-app-bar-nav-icon>
      </template>
      <template v-slot:append>
        <v-btn icon="mdi-heart"></v-btn>

        <v-btn icon="mdi-magnify"></v-btn>

        <v-btn icon="mdi-dots-vertical"></v-btn>
      </template>
    </v-app-bar>

    <v-main class="pl-20"><RouterView /></v-main>
  </v-layout>
</template>

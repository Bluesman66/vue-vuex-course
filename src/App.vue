<template>
  <v-app>
    <v-container>
      <Navbar />
      <router-view />
    </v-container>
  </v-app>
</template>

<script>
import Navbar from './components/Navbar';
export default {
  components: { Navbar },
  name: "App",
};
</script>

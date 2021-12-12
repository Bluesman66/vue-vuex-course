<template>
  <v-dialog
    v-model="$store.getters.getDialogVisible"
    persistent
    max-width="600"
  >
    <v-card @click="hideDialog">
      <v-card-title>{{ fullTitle }}</v-card-title>
      <v-card-text>
        <v-img :src="$store.getters.getCurrentPhoto.url" />
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  methods: {
    hideDialog() {
      this.$store.commit("hideDialog");
    },
  },

  computed: {
    fullTitle() {
      return `Image name - ${this.$store.getters.getCurrentPhoto.title}`;
    },
  },
};
</script>

<style  scoped>
</style>
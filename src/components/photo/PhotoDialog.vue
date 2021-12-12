<template>
  <v-dialog v-model="dialogVisible" persistent max-width="600">
    <v-card @click="closeDialog">
      <v-card-title>{{ photo.title }}</v-card-title>
      <v-card-text>
        <v-img :src="photo.url" />
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: {
    photo: {
      type: Object,
      required: true,
    },
    dialogVisible: {
      type: Boolean,
      default: false,
    },
  },

  methods: {
    closeDialog() {
      this.$emit("closeDialog");
    }
  }
};
</script>

<style  scoped>
</style>
<template>
  <v-container
    ><Photo v-bind:key="photo.id" v-for="photo in photos" v-bind:photo="photo"
  /></v-container>
</template>

<script>
import Photo from "../components/photo/Photo";
export default {
  components: { Photo },
  data: () => ({
    photos: [
      { id: 1, title: "photo 1" },
      { id: 2, title: "photo 2" },
      { id: 3, title: "photo 3" },
      { id: 4, title: "photo 4" },
    ],
  }),
};
</script>

<style  scoped>
</style>
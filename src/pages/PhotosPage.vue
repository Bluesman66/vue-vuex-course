<template>
  <v-container>
    <PhotoForm @addPhoto="addPhoto" />
    <v-row>
      <Photo :key="photo.id" v-for="photo in photos" :photo="photo" />
    </v-row>
  </v-container>
</template>

<script>
import Photo from "../components/photo/Photo";
import PhotoForm from "../components/photo/PhotoForm";

export default {
  components: { Photo, PhotoForm },

  data: () => ({
    photos: [],
  }),

  methods: {
    fetchTodo() {
      this.axios
        .get("https://jsonplaceholder.typicode.com/photos?_limit=10")
        .then((response) => (this.photos = response.data));
    },

    addPhoto(photo) {
      this.photos.push(photo);
    },
  },

  mounted() {
    this.fetchTodo();
  },
};
</script>

<style  scoped>
</style>
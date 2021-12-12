<template>
  <v-container>
    <v-row>
      <Photo
        :key="photo.id"
        v-for="photo in photos"
        :photo="photo"
      />
    </v-row>
  </v-container>
</template>

<script>
import Photo from "../components/photo/Photo";
export default {
  components: { Photo },

  data: () => ({
    photos: [],
  }),

  methods: {
    fetchTodo() {
      this.axios
        .get("https://jsonplaceholder.typicode.com/photos?_limit=10")
        .then((response) => (this.photos = response.data));
    },
  },

  mounted() {
    this.fetchTodo();
  },
};
</script>

<style  scoped>
</style>
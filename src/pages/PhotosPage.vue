<template>
  <v-container>
    <PhotoForm v-if="photos.length < 11" @addPhoto="addPhoto" />
    <div v-else>You can't add any photo anymore</div>
    <v-row>
      <Photo
        :key="photo.id"
        v-for="photo in photos"
        :photo="photo"
        @openPhoto="openPhoto"
      />
    </v-row>
    <PhotoDialog
      :photo="currentPhoto"
      :dialogVisible="dialogVisible"
      @closeDialog="closeDialog"
    />
  </v-container>
</template>

<script>
import Photo from "../components/photo/Photo";
import PhotoForm from "../components/photo/PhotoForm";
import PhotoDialog from "../components/photo/PhotoDialog";

export default {
  components: { Photo, PhotoForm, PhotoDialog },

  data: () => ({
    photos: [],
    currentPhoto: {},
    dialogVisible: false,
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

    openPhoto(photo) {
      this.currentPhoto = photo;
      this.dialogVisible = true;
    },

    closeDialog() {
      this.dialogVisible = false;
    }
  },

  mounted() {
    this.fetchTodo();
  },
};
</script>

<style  scoped>
</style>
<template>
  <v-container>
    <PhotoForm />
    <v-row>
      <Photo
        :key="photo.id"
        v-for="photo in $store.getters.getAllPhotos"
        :photo="photo"
      />
    </v-row>
    <PhotoDialog />
  </v-container>
</template>

<script>
import Photo from "../components/photo/Photo";
import PhotoForm from "../components/photo/PhotoForm";
import PhotoDialog from "../components/photo/PhotoDialog";

export default {
  components: { Photo, PhotoForm, PhotoDialog },

  mounted() {
    this.$store.dispatch("fetchPhotos");
  },
};
</script>

<style  scoped>
</style>
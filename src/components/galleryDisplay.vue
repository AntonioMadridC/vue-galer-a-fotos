<template>
  <div v-if="selectedPicture">
    <div class="container d-flex ps-5 pt-5">
      <div class="description_image">
        <img :src="selectedPicture.src" alt="" class="pb-2 pt-3" />
        <p>Autor: {{ selectedPicture.author }}</p>
        <button class="btn btn-secondary mt-4" @click="$emit('closeDisplay')">
          Cerrar
        </button>
      </div>
      <div class="description_text ms-5">
        <p>{{ selectedPicture.description }} {{ selectedPicture.description }} <br> <a :href="selectedPicture.src">link de la foto</a> </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "gallery-display",
  props: {
    selectedPicture: {
      type: Object,
      required: true,
    },
  },
  data: function () {
    return {};
  },
  // computed: {},
  //methods: {}
  // watch: {},
  // components: {},
  // mixins: [],
  // filters: {},
  // -- Lifecycle Methods
  // -- End Lifecycle Methods
};
</script>

<style scoped>
.description_image {
  width: 50%;
}

img {
  width: 100%;
  height: auto;

}

.description_text {
  width: 40%;
  max-height: 500px;
  overflow: auto;
  border: solid 1px black;
}
</style>
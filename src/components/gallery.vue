<template>
  <div class="contenedor">
    <div class="pictures_section">
      <nav
        class="navbar bg-light border-bottom border-bottom-dark justify-content-center"
        data-bs-theme="dark"
      >
        <h1 class="text-center">Galería</h1>
      </nav>
      <div class="pictures">
        <div>
          <div
            class="gallery_pictures"
            v-for="(picture, index) in pictures"
            :key="index"
          >
            <img
              @click="showDescription(picture.id)"
              :src="picture.src"
              alt="image_picture"
            />
          </div>
        </div>
      </div>
    </div>

    <div class="description">
      <nav
        class="navbar bg-secondary border-bottom border-bottom-dark"
        data-bs-theme="dark"
      >
        <h3 class="ps-3">Descripción</h3>
      </nav>
      <gallery-display
        :selectedPicture="selectedPicture"
        @closeDisplay="selectedPicture = null"
      ></gallery-display>
    </div>
  </div>
</template>

<script>
import galleryDisplay from "./galleryDisplay.vue";
export default {
  components: { galleryDisplay },
  name: "gallery-scroll",
  // props: {},
  data: function () {
    return {
      pictures: [
        {
          id: 1,
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam ornare porttitor sem in imperdiet. Nam tempor porta metus nec condimentum. Phasellus eu aliquet est. Donec hendrerit ultrices lacus nec ullamcorper. Aliquam sodales ante nec venenatis lobortis. Pellentesque quis risus eget mauris porttitor molestie. Mauris feugiat sagittis feugiat. Mauris convallis eget risus a fringilla. Sed odio turpis, egestas in diam ac, scelerisque congue nulla. Nulla porta urna ex, eu pretium orci finibus ut. Donec quis dictum arcu. Sed hendrerit arcu molestie quam ultricies, eu auctor eros vulputate. Maecenas ullamcorper augue nec bibendum fermentum. ",
          src: "https://picsum.photos/id/684/400/400",
          author: "loco de la montaña",
        },
        {
          id: 2,
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam ornare porttitor sem in imperdiet. Nam tempor porta metus nec condimentum. Phasellus eu aliquet est. Donec hendrerit ultrices lacus nec ullamcorper. Aliquam sodales ante nec venenatis lobortis. Pellentesque quis risus eget mauris porttitor molestie. Mauris feugiat sagittis feugiat. Mauris convallis eget risus a fringilla. Sed odio turpis, egestas in diam ac, scelerisque congue nulla. Nulla porta urna ex, eu pretium orci finibus ut. Donec quis dictum arcu. Sed hendrerit arcu molestie quam ultricies, eu auctor eros vulputate. Maecenas ullamcorper augue nec bibendum fermentum. ",
          src: "https://picsum.photos/id/685/400/400",
          author: "amigo del loco de la montaña",
        },
        {
          id: 3,
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam ornare porttitor sem in imperdiet. Nam tempor porta metus nec condimentum. Phasellus eu aliquet est. Donec hendrerit ultrices lacus nec ullamcorper. Aliquam sodales ante nec venenatis lobortis. Pellentesque quis risus eget mauris porttitor molestie. Mauris feugiat sagittis feugiat. Mauris convallis eget risus a fringilla. Sed odio turpis, egestas in diam ac, scelerisque congue nulla. Nulla porta urna ex, eu pretium orci finibus ut. Donec quis dictum arcu. Sed hendrerit arcu molestie quam ultricies, eu auctor eros vulputate. Maecenas ullamcorper augue nec bibendum fermentum. ",
          src: "https://picsum.photos/id/686/400/400",
          author: "cocinero aburrido",
        },
      ],
      selectedPicture: null,
    };
  },
  // computed: {},
  methods: {
    showDescription(id) {
      const picture = this.pictures.find((picture) => picture.id == id);
      console.log(picture);
      this.selectedPicture = picture;
    },
  },
  // watch: {},
  // components: {},
  // mixins: [],
  // filters: {},
  // -- Lifecycle Methods
  // -- End Lifecycle Methods
};
</script>

<style scoped>
.contenedor {
  width: 80%;
  border: 1px solid black;
  margin: 0 auto;
  display: flex;
}

.pictures_section {
  flex-basis: 40%;
}

.navbar {
  height: 5rem;
}

.pictures {
  max-height: 600px;
  overflow: auto;
}

.gallery_pictures {
  width: 70%;
  margin: 40px auto;
  border: 3px solid grey;
  height: 250px;
}
img {
  width: 100%;
  max-height: 100%;
}

.description {
  flex-basis: 60%;
}
</style>
<!-- MockupPreview.vue -->
<template>
  <div
    class="mockup-container d-flex justify-content-center align-items-center"
  >
    <img class="tshirt-image" :src="tshirtImageUrl" alt="T-Shirt" />
    <img
      v-if="logo"
      :src="combinedImageUrl"
      class="logo"
      alt="Mockup Preview"
    />
  </div>
</template>

<script>
export default {
  props: {
    logo: {
      type: String,
      default: "",
    },
  },
  computed: {
    tshirtImageUrl() {
      return "/tshirt.png";
    },
    combinedImageUrl() {
      return this.logo ? this.logo : "";
    },
  },
};
</script>

<style scoped>
.mockup-container {
  position: relative;
}

.logo {
  position: absolute;
  max-width: 35%;
  max-height: 35%;
  mix-blend-mode: multiply;
}

@media (max-width: 1200px) {
  .logo {
    max-width: 60%;
    max-height: 60%;
  }
}

@media (max-width: 768px) {
  .logo {
    max-width: 30%; /* Adjust the logo size for smaller screens */
    max-height: 30%;
  }
}
</style>

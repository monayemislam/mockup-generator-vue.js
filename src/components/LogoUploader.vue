<!-- LogoUploader.vue -->
<template>
  <input type="file" @change="handleLogoUpload" />
</template>
  
  <script>
export default {
  methods: {
    handleLogoUpload(event) {
      const file = event.target.files[0];
      this.$emit("logo-uploaded", file);
    },
  },
};
</script>
  
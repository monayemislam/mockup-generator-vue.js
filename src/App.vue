<!-- YourMainComponent.vue -->
<template>
  <div
    class="d-flex flex-column justify-content-center align-items-center py-4"
  >
    <h2>Mockup Generator</h2>
    <MockupPreview :logo="uploadedLogo" />
    <LogoUploader @logo-uploaded="handleLogoUploaded" />
  </div>
</template>

<script>
import LogoUploader from "@/components/LogoUploader.vue";
import MockupPreview from "@/components/MockupPreview.vue";

export default {
  components: {
    LogoUploader,
    MockupPreview,
  },
  data() {
    return {
      uploadedLogo: null,
    };
  },
  methods: {
    handleLogoUploaded(logo) {
      this.uploadedLogo = URL.createObjectURL(logo);
    },
  },
};
</script>

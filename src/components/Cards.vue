<template>
  <v-hover v-slot="{ isHovering, props }">
    <VCard
      class="ma-2 pa-4"
      elevation="4"
      v-bind="props"
      :elevation="isHovering ? 24 : 12"
    >
      <VImg
        :src="job.logo"
        :lazy-src="job.logo"
        height="70"
        class="align-end ma-6"
      >
        <template v-slot:placeholder>
          <VRow class="fill-height ma-0" align="center" justify="center">
            <VProgressCircular
              indeterminate
              color="grey-lighten-5"
            ></VProgressCircular>
          </VRow>
        </template>
      </VImg>
      <VCardSubtitle>{{ job.name }}</VCardSubtitle>
      <VCardActions>
        <v-btn
          size="x-small"
          rounded="xl"
          elevation="2"
          @click="copyUrl(job.url)"
        >
          Copy Link Page
        </v-btn>
        <v-btn
          size="x-small"
          @click="openNewUrl(job.url)"
          rounded="xl"
          elevation="2"
        >
          Visit page
        </v-btn>
      </VCardActions>
    </VCard>
  </v-hover>
</template>

<script setup>
import {
  VCardActions,
  VCardSubtitle,
  VProgressCircular,
} from "vuetify/lib/components/index.mjs";

const props = defineProps({
  job: Object,
});

const openNewUrl = (url) => {
  const newTab = window.open(url, "_blank");
  newTab.focus();
};

const copyUrl = (url) => {
  navigator.clipboard.writeText(url);
};

// export default {
//   props: {
//     job: Object, // El objeto que representa un trabajo remoto
//   },
//   components: { VCardActions, VProgressCircular, VCardSubtitle },
//   methods: {
//     openNewUrl(url) {
//       const newTab = window.open(url, "_blank");
//       newTab.focus();
//     },
//     copyUrl(url) {
//       navigator.clipboard.writeText(url);
//     },
//   },
// };
</script>

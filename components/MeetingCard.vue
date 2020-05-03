<template>
  <div>
    <v-card style="max-width: 60vw">
      <v-card-title class="headline">
        {{ title }}
      </v-card-title>
      <v-card-text>
        <div class="iframe-container">
          <iframe
            v-if="embedType === 'iframe'"
            :src="src"
            frameborder="0"
          />
        </div>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
export default {
  props: {
    title: { type: String, required: true },
    src: { type: String, required: true },
    embedType: { type: String, default: 'iframe' }
  }

}
</script>

<style scoped>
  .iframe-container {
  overflow: hidden;
  padding-top: 56.25%;
  position: relative;
}

.iframe-container iframe {
   border: 0;
   height: 100%;
   left: 0;
   position: absolute;
   top: 0;
   width: 100%;
}
</style>

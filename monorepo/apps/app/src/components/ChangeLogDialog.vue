<template>
  <v-dialog v-model="isOpen" max-width="480">
    <v-card title="Change Log">
      <!-- eslint-disable-next-line vue/no-v-html -->
      <v-card-text class="change-log" v-html="changeLogHtml" />

      <v-card-actions>
        <v-spacer />
        <v-btn text="Close" @click="isOpen = false" />
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script lang="ts" setup>
  import { marked } from 'marked'
  import changeLog from '../../CHANGELOG.md?raw'

  const isOpen = defineModel<boolean>({ required: true })

  const changeLogHtml = marked.parse(changeLog, { async: false })
</script>

<style scoped>
  .change-log :deep(h1) {
    font-size: 1.25rem;
    margin-bottom: 0.5em;
  }

  .change-log :deep(h2) {
    font-size: 1.1rem;
    margin-top: 1em;
    margin-bottom: 0.25em;
  }

  .change-log :deep(h3) {
    font-size: 1rem;
    margin-top: 0.5em;
    margin-bottom: 0.25em;
  }

  .change-log :deep(ul) {
    padding-left: 1.25em;
  }

  .change-log :deep(p) {
    margin-bottom: 0.5em;
  }
</style>

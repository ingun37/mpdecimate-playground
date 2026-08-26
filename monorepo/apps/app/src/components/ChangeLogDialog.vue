<template>
  <v-dialog v-model="isOpen" max-width="480">
    <v-card title="Change Log">
      <v-card-text class="change-log">{{ changeLog }}</v-card-text>

      <v-card-actions>
        <v-spacer />
        <v-btn text="Close" @click="isOpen = false" />
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script lang="ts" setup>
  import changeLog from '../../CHANGELOG.md?raw'

  const isOpen = defineModel<boolean>({ required: true })
</script>

<style scoped>
  .change-log {
    white-space: pre-wrap;
    font-family: monospace;
  }
</style>

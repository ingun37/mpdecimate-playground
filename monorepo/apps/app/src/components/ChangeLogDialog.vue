<template>
  <v-dialog v-model="isOpen" max-width="480">
    <v-card title="Change Log">
      <v-card-text>
        Coming soon
      </v-card-text>

      <v-card-actions>
        <v-spacer />
        <v-btn text="Close" @click="isOpen = false" />
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script lang="ts" setup>
  const isOpen = defineModel<boolean>({ required: true })
</script>

<template>
  <n-card>
    <p>{{props.archiveItem.name}}</p>
  </n-card>
</template>

<script setup lang="ts">

const props = defineProps<{archiveItem: Record<string, any>}>()

</script>

<style lang="scss">
.n-card {
  border-radius: 1rem;
}

</style>

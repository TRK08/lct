<template>
  <n-card hoverable style="cursor: pointer">
    <p>Название файла{{props.archiveItem.name}}</p>
    <small>Дата: {{date}}</small>
  </n-card>
</template>

<script setup lang="ts">

import {computed} from "vue";

const props = defineProps<{archiveItem: Record<string, any>}>()


const date = computed(() => {
  return new Date(props.archiveItem.created).toLocaleString()
})
</script>

<style lang="scss">
.n-card {
  border-radius: 1rem;
}

</style>

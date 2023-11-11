<template>
  <n-card>
    <n-input
        v-model:value="RTSPLink"
        placeholder="Введите ссылку на RTSP поток"
        :theme-overrides="theme === null ? inputThemeOverridesLight: inputThemeOverridesDark"
    />
    <n-button
        type="primary"
        style="width: 100%; margin-top: 1rem"
    >Отправить</n-button>
  </n-card>
</template>

<script setup lang="ts">
import type {InputProps} from "naive-ui";
import {useGlobalStore} from "@/stores";
import {storeToRefs} from "pinia";
import {ref} from "vue";

type InputThemeOverrides = NonNullable<InputProps['themeOverrides']>
const {theme} = storeToRefs(useGlobalStore())

const inputThemeOverridesLight: InputThemeOverrides = {
  color: '#FFFFFF'
}
const inputThemeOverridesDark: InputThemeOverrides = {
  color: '#333333'
}

const RTSPLink = ref('')

</script>

<style lang="scss">

</style>

<script setup lang="ts">
import { darkTheme, NConfigProvider } from 'naive-ui'
import { naiveThemeOverrides } from '@/theme/naive'
</script>

<template>
  <NConfigProvider
    :theme="darkTheme"
    :theme-overrides="naiveThemeOverrides"
  >
    <RouterView />
  </NConfigProvider>
</template>
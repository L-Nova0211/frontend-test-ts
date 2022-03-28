<template>
  <div>
    <h1>{{ `Error - ${statusCode}` }}</h1>
    <p>{{ message }}</p>
  </div>
</template>

<script setup lang="ts">
interface Props {
  title?: string
  message?: string
  statusCode?: number
}

withDefaults(defineProps<Props>(), {
  title: 'Not Found',
  message: "We're sorry, but this page doesn't exist.",
  statusCode: 404,
})
</script>

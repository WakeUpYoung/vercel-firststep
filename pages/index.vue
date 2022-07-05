<script setup>
import { ref, useFetch } from '#imports'

const name = ref('This is a default data')
 const onClickButton = async () => {
   const { data } = await useFetch(() => `/api/helloworld`)
   name.value = data
 }
</script>

<template>
  <div>
    {{ name }}
  </div>
  <button @click="onClickButton">Fetch Data</button>
</template>

<style scoped>
div {
  color: rosybrown;
}
</style>

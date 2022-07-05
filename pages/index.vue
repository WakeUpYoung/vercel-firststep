<script setup>
import { ref, useFetch } from '#imports'

const name = ref('This is a default data')
 const onClickButton = async () => {
   const { data } = await useFetch(() => `/api/helloworld`)
   console.log(data)
   name.value = data.value ? data.value : 'error'
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

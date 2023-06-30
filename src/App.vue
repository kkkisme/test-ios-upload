<script setup>

import {onMounted, ref} from 'vue'

const res = ref()

onMounted(() => {
  document.body.addEventListener('click', () => {
    console.log(res.value)
  })
})

const handleUpload = () => {
  navigator.geolocation.getCurrentPosition((info) => {
    res.value = info
  }, (err) => {
    console.log(err)
  })
}
</script>

<template>
  <van-uploader @click-upload="handleUpload" capture="true">

  </van-uploader>
</template>

<style scoped>

</style>

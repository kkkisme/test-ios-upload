<script setup>

import {onMounted, ref} from 'vue'

const res = ref()

onMounted(() => {
  document.body.addEventListener('click', () => {
    console.log(res.value)
  })
})

const handleUpload = () => {
  console.log('start get loc')
  navigator.geolocation.getCurrentPosition((info) => {
    console.log('success get', info)
    res.value = info
  }, (err) => {
    console.log('fail', err)
  })
}
</script>

<template>
  <van-uploader @click-upload="handleUpload" capture="true">

  </van-uploader>
</template>

<style scoped>

</style>

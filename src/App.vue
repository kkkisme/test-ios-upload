<script setup>

import {ref} from 'vue'

const res = ref()

const clickButton = () => {
  console.log('body click', res.value)
}
const clickButton2 = () => {
  navigator.geolocation.getCurrentPosition((info) => {
    console.log('btn success get', info)
  }, (err) => {
    console.log('btn fail', err)
  })
}

const handleUpload = () => {
  console.log('start get loc')
  setTimeout(() => {
    navigator.geolocation.getCurrentPosition((info) => {
      console.log('success get', info)
      res.value = info
    }, (err) => {
      console.log('fail', err)
    })
  }, 200)
}
</script>

<template>
  <van-button @click="clickButton">btn1</van-button>
  <van-button @click="clickButton2">btn2</van-button>
  <van-uploader @click-upload="handleUpload" capture="true"></van-uploader>
</template>

<style scoped>

</style>

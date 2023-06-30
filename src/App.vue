<script setup>

import {ref} from 'vue'

const res = ref()

const clickButton = () => {
  console.log('btn1 click', res.value)
}
const clickButton2 = () => {
  console.log('btn2 click')
  navigator.geolocation.getCurrentPosition((info) => {
    console.log('btn2 success get', info)
  }, (err) => {
    console.log('btn2 fail', err)
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
  <br />
  <van-button @click="clickButton2">btn2</van-button>
  <br />
  <van-uploader @click-upload="handleUpload" capture="true"></van-uploader>
</template>

<style scoped>

</style>

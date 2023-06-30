<script setup>

const handleUpload = () => {
  navigator.geolocation.getCurrentPosition((res) => {
    console.log(res)
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

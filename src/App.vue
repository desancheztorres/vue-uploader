<template>
  <div id="app" class="container">
    <Uploader
      :options="{
        baseURL: 'http://desancheztorres.com/projects/vue-uploader/api/public/api'
      }"
      :handlers="{
        'video/mp4' : {
          endpoint: 'uploads/video'
        }
      }"
    />
  </div>
</template>

<script>
import Uploader from '@/uploader/components/Uploader';

export default {
  name: 'app',
  components: {
    Uploader
  }
}
</script>

<style src="@/assets/styles/app.css"/>

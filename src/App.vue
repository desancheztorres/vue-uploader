<template>
  <div id="app" class="container">
    <Uploader />
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

<template>
  <div>
    <h1 class="title">文字数カウンター</h1>
    <p>下記のテキストボックスに書き込んでください</p>
    <textarea v-model="text" name="text" id="text" cols="100" rows="20"></textarea>
    <p>文字数：{{text.length}}</p>
    <a href="/list">戻る</a>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      text: ""
    }
  }
})
</script>

<style scoped>
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 50px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>

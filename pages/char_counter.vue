<template>
  <div>
    <textarea v-model="text" name="text" id="text" cols="30" rows="10"></textarea>
    <p>文字数：{{text.length}}</p>
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

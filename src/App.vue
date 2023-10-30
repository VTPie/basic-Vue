<script setup>
  import { ref } from 'vue';
  import Child from './components/Child.vue';
  import OtherChild from './components/OtherChild.vue'
  import OtherOtherChild from './components/OtherOtherChild.vue'

  const postFontSize = ref(1)
  const currentTab = ref('OtherChild')
  const tabs = {
    OtherChild,
    OtherOtherChild
  }
</script>

<template>
  <h1>This is my basic-vue project</h1>
  <div :style="{ fontSize: postFontSize + 'em' }">
    <Child name="Phong" @enlargeText="postFontSize += 0.1">
      This is content distribution with slots
    </Child>
  </div>
  <div class="demo">
    <button
       v-for="(_, tab) in tabs"
       :key="tab"
       @click="currentTab = tab"
     >
      {{ tab }}
    </button>
	  <component :is="tabs[currentTab]"></component>
  </div>
</template>

<style>
</style>

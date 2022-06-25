<template>
  <h1>{{ msg }}</h1>

  <p>
    Recommended IDE setup:
    <a href="https://code.visualstudio.com/" target="_blank">VS Code</a>
    +
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
  </p>

  <p>See <code>README.md</code> for more information.</p>

  <p>
    <a :style="aElStyle" @click="test" target="_blank">
      Vite Docs
    </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Docs</a>
  </p>

  <button type="button" @click="count++">count is: {{ count }}</button>
  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<script setup lang="ts">
  import { ref, reactive, computed } from "vue";

  defineProps<{ msg: string }>();

  const count = ref(0);
  const color = ref<string>('red')
  const aElStyle = computed(() => {color: color.value})
  const plusOne = computed(() => count.value + 1)

  function test(){
    console.log('测试计算属性', aElStyle, color.value, plusOne.value);
    
  }
</script>

<style scoped lang="scss">
a {
  color: v-bind(color);
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>

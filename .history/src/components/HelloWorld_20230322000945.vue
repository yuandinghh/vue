<script setup lang="ts">
import { defineProps } from "vue";
import { computed, reactive } from "vue";
defineProps<{
  msg: string;
}>();
    const state = reactive({
      count: 0,
      str:"hello world",
      str1:"你好袁丁"
    });

    const increment = () => {
      state.count++;
    };
     const str2 = computed(() => {
      return state.str + state.str1;
    }); 

    const str3 = state.str + state.str1;
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <button @click="increment" class="btn btn-primary"> increment</button>
    <h3>{{state.count}}</h3>
    <h3>{{str2}}</h3>
    <h3>{{str3}}</h3>
    <h3>
      You’ve successfully created a project with
      <a
        href="https://vitejs.dev/"
        target="_blank"
        rel="noopener"
      >Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>. What's next?
    </h3>
    <!-- <p>{{ str }}</p> -->
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>

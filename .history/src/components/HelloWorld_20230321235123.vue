

<script setup lang="ts">
import { defineProps } from "vue";
import { computed, reactive } from "vue";

defineProps<{
  msg: string;
}>();

// export default {
//  setup() {
    const state = reactive({
      count: 0,
    });

    const increment = () => {
      state.count++;
    };

    // return {
    //   ...state,
    //   increment,
    // };

 //  },
// };
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <button @click="increment" class="btn btn-primary"> increment</button>
    <h1>{{state.count}}mes</h1>
    <h3>
      You’ve successfully created a project with
      <a
        href="https://vitejs.dev/"
        target="_blank"
        rel="noopener"
      >Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>. What's next?
    </h3>
    <p>{{ count }}</p>
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

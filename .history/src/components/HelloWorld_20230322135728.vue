<script setup lang="ts">
import { defineProps } from "vue";
import { computed, reactive } from "vue";
 defineProps<{  //defineProps 是只在 <script setup> 中才能使用的 编译器宏 。 他们不需要导入且会随着 <script setup> 处理过程一同被编译掉。 defineProps 接收与 props 选项 相同的值。 他们会被编译为 props 选项。 但是，它们不会被暴露给模板，因为 <script setup> 中的模板是静态的。 你可以使用 defineProps 来定义类型，但是不要使用它来定义默认值。 你可以使用 defineEmits 来定义 emit 类型。 你可以使用 defineExpose 来定义暴露的类型。 你可以使用 defineProps 来定义 props 类型。 你可以使用 defineEmits 来定义 emit 类型。 你可以使用 defineExpose 来定义暴露的类型。 你可以使用 
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
    const str3 = state.str + state.str1;//不需要return


</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <button @click="increment" class="btn btn-primary"> increment</button>
    <h3>{{state.count}}</h3>
    <h3>{{str2}}</h3>
    <h3>{{str3}}</h3>
    <!-- <h3>
      You’ve successfully created a project with
      <a
        href="https://vitejs.dev/"
        target="_blank"
        rel="noopener"
      >Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>. What's next?
    </h3> -->
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

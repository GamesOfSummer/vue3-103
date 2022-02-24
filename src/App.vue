<script setup lang="ts">
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "@/components/HelloWorld.vue";
import { reactive, ref, defineComponent, computed, watch } from "vue";

const author = reactive({
  getTaco: false,
});

function getTaco(event) {
  console.log("clicked");
  author.getTaco = !author.getTaco;
}

// watch works directly on a ref
watch(getTaco, async (newQuestion, oldQuestion) => {
  console.log("clicked again!");
});
</script>

<template>
  <div>
    <button @click="getTaco">Click me to order a taco</button>
    <h2>Where is my taco...</h2>
  </div>
</template>

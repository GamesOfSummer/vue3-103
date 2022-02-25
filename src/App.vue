<script setup lang="ts">
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "@/components/HelloWorld.vue";
import { reactive, ref, defineComponent, computed, watch } from "vue";

let getTaco = true;
const question = ref("");

function getTacoClick(event) {
  console.log("clicked");
  getTaco = !getTaco;
}

// watch works directly on a ref
watch(getTaco, async (newQuestion, oldQuestion) => {
  console.log("clicked again!");
});

// watch works directly on a ref
watch(question, async (newQuestion, oldQuestion) => {
  console.log("clicked again!");
});
</script>

<template>
  <div>
    <button @click="getTacoClick">Click me to order a taco</button>
    <h2>Where is my taco...</h2>
  </div>

  <input v-model="question" />
</template>

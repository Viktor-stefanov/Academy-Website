<template>
  <div class="relative flex items-center justify-center h-screen">
    <!-- Left navigation button with absolute positioning -->
    <v-btn icon class="absolute left-4" @click="prevReview">
      <v-icon>mdi-chevron-left</v-icon>
    </v-btn>

    <!-- Review card centered on the screen -->
    <v-card
      class="rounded-lg shadow-lg hover:shadow-2xl transition duration-300 ease-in-out"
      style="width: 40%"
      v-if="reviews.length > 0"
    >
      <v-card-title>{{ reviews[currentIndex].name }}</v-card-title>
      <v-card-text>{{ reviews[currentIndex].text }}</v-card-text>
    </v-card>

    <!-- Right navigation button with absolute positioning -->
    <v-btn icon class="absolute right-4" @click="nextReview">
      <v-icon>mdi-chevron-right</v-icon>
    </v-btn>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";

interface Review {
  name: string;
  text: string;
}

const currentIndex = ref<number>(0);
const reviews = ref<Array<Review>>([
  { name: "Alice", text: "This course helped me land my first internship with ease!" },
  { name: "Bob", text: "Thanks to these certificates, I thoroughly enjoyed my learning process!" },
  {
    name: "Viktor",
    text: "Thanks to these certificates, I thoroughly enjoyed my learning process!",
  },
  { name: "Ddz", text: "Thanks to these certificates, I thoroughly enjoyed my learning process!" },
]);

const nextReview = () => {
  currentIndex.value = (currentIndex.value + 1) % reviews.value.length;
};

const prevReview = () => {
  currentIndex.value = (currentIndex.value - 1 + reviews.value.length) % reviews.value.length;
};

let intervalId: number | undefined;
onMounted(() => {
  intervalId = setInterval(nextReview, 3000); // Automatically switch reviews every 3 seconds
});

onUnmounted(() => {
  if (intervalId) clearInterval(intervalId);
});
</script>

<style scoped>
@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
.spin-animation {
  animation: spin 3s linear infinite;
}
</style>

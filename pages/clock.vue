<template>
  <div>
    <h1 class="text-2xl font-semibold">เวลาปัจจุบัน</h1>
    <p>{{ time }}</p>
  </div>
  <div>
    <button @click="toggleDarkMode" class="p-2 rounded-md border border-black">
      {{ darkModeText }}
    </button>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

useHead({
  title: "Clock",
});

const time = ref("");
const darkModeText = ref("โหมดกลางคืน");

const setTime = () => {
  const now = new Date();
  const hour = String(now.getHours()).padStart(2, "0");
  const minute = String(now.getMinutes()).padStart(2, "0");
  const second = String(now.getSeconds()).padStart(2, "0");
  time.value = `${hour}:${minute}:${second}`;
};

onMounted(() => {
  setTime();
  setInterval(setTime, 1000);
});

const toggleDarkMode = () => {
  const isDark = document.body.classList.toggle("dark");
  darkModeText.value = isDark ? "โหมดกลางวัน" : "โหมดกลางคืน";
};
</script>

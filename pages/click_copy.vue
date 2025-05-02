<template>
    <div
      class="flex flex-col items-center justify-center h-screen gap-2"
    >
      <h1 class="text-white text-2xl font-semibold">
        Click enroll cupon code 50%
      </h1>
      <div class="flex">
        <input
          type="text"
          v-model="couponCode"
          class="border border-white rounded-l-md p-2 bg-slate-400"
        />
        <button
          @click="copy"
          ref="button"
          class="border border-white rounded-r-md p-2 bg-white text-slate-600 hover:bg-slate-600 hover:text-white"
        >
          Copy
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
  useHead({
    title: "Click to Copy",
  });
  
  const couponCode = ref("Sale50");
  const button = ref(null);
  
  const copy = () => {
    navigator.clipboard.writeText(couponCode.value);
    if (button.value) {
      button.value.textContent = "Copied";
      setTimeout(() => {
        button.value.textContent = "Copy";
      }, 2000);
    }
    console.log(couponCode.value);
  };
  
  /* watch(couponCode, () => {
          console.log(couponCode.value)
      }) */
  
  </script>
  
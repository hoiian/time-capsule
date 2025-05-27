<template>
  <div
    class="h-screen w-full bg-black text-white flex flex-col justify-between p-6 relative overflow-hidden"
  >
    <!-- 題目與說明 -->
    <div class="z-10">
      <h1 class="text-3xl font-bold mb-2">未來信箱</h1>
      <p class="text-sm text-white/80">俾未來嘅自己，寄一封信</p>
    </div>

    <!-- 虛化膠囊背景 -->
    <div class="absolute inset-0 z-0">
      <!-- <img
        src="/your-blur-capsule-image.png"
        alt="背景"
        class="w-full h-full object-cover blur-2xl opacity-60"
      /> -->
    </div>

    <!-- 按鈕區 -->
    <div class="z-10 flex flex-col gap-4">
      <NuxtLink
        to="/select"
        class="bg-yellow-400 text-black font-medium text-center py-3 rounded-lg shadow hover:bg-yellow-300 transition"
      >
        想留俾自己
      </NuxtLink>

      <NuxtLink
        to="/login"
        class="bg-neutral-800 text-white text-center py-3 rounded-lg border border-white/10 hover:bg-neutral-700 transition"
      >
        搵返自己
      </NuxtLink>
    </div>
  </div>
</template>

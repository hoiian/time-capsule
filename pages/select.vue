<template>
  <div
    class="min-h-screen bg-zinc-950 text-white p-6 flex flex-col justify-center relative"
  >
    <!-- 返回箭頭 -->
    <button
      @click="$router.back()"
      class="absolute top-6 left-6 text-white text-2xl mb-4"
    >
      ←
    </button>

    <!-- 留下的內容選擇 -->
    <div class="space-y-8 z-10">
      <div>
        <p class="text-3xl mb-3">我想留</p>
        <div class="flex gap-3">
          <button
            :class="type === 'text' ? activeBtn : inactiveBtn"
            @click="type = 'text'"
          >
            文字
          </button>
          <button
            :class="type === 'voice' ? activeBtn : inactiveBtn"
            @click="type = 'voice'"
          >
            語音
          </button>
        </div>
      </div>

      <div>
        <p class="text-3xl mb-3">俾</p>
        <div class="flex flex-wrap gap-3">
          <button
            v-for="option in timeOptions"
            :key="option.value"
            :class="selectedTime === option.value ? activeBtn : inactiveBtn"
            @click="selectedTime = option.value"
          >
            {{ option.label }}
          </button>
        </div>
      </div>

      <div>
        <p class="text-3xl mb-3">嘅</p>
        <div class="flex gap-3">
          <button
            :class="target === 'self' ? activeBtn : inactiveBtn"
            @click="target = 'self'"
          >
            自己
          </button>
          <button
            :class="target === 'friend' ? activeBtn : disabledBtn"
            disabled
          >
            朋友
          </button>
        </div>
      </div>
    </div>

    <!-- 前往創建頁 -->
    <NuxtLink
      to="/create"
      class="absolute bottom-6 right-6 bg-white text-black w-14 h-14 rounded-full flex items-center justify-center text-2xl shadow-md"
    >
      →
    </NuxtLink>
  </div>
</template>

<script setup>
import { ref } from "vue";

const type = ref("text");
const selectedTime = ref("1m");
const target = ref("self");

const timeOptions = [
  { label: "一個月後", value: "1m" },
  { label: "三個月後", value: "3m" },
  { label: "半年後", value: "6m" },
  { label: "一年後", value: "1y" },
  { label: "自訂時間", value: "custom" },
];

const activeBtn =
  "bg-white text-black px-4 py-2 rounded-full font-medium text-sm";
const inactiveBtn =
  "border border-white px-4 py-2 rounded-full text-sm text-white/80";
const disabledBtn =
  "border border-white/30 px-4 py-2 rounded-full text-sm text-white/30";
</script>

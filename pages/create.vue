<template>
  <div
    class="min-h-screen bg-black text-white p-6 flex flex-col justify-between relative"
  >
    <!-- 留言框區域 -->
    <div class="mt-6">
      <p class="text-white/70 mb-2">留低你嘅文字，未來會告訴你答案……</p>
      <div class="relative">
        <textarea
          v-model="message"
          placeholder="..."
          class="w-full h-64 p-4 bg-black border border-white/20 rounded-xl resize-none text-sm placeholder-white/30"
        ></textarea>

        <!-- 附加圖片 icon -->
        <button class="absolute bottom-4 right-4 bg-white/10 p-3 rounded-full">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="w-6 h-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 16l4-4 4 4m0 0l4-4 4 4m-4-4v12"
            />
          </svg>
        </button>
      </div>
    </div>

    <!-- 提交按鈕 -->
    <button
      class="mt-6 bg-yellow-400 text-black font-medium w-full py-4 rounded-xl text-center flex items-center justify-center gap-2"
      @click="submit"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="w-5 h-5"
        viewBox="0 0 24 24"
        fill="currentColor"
      >
        <path d="M2 21l21-9L2 3v7l15 2-15 2v7z" />
      </svg>
      寄俾{{ label }}
    </button>
  </div>
</template>

<script setup>
import { ref } from "vue";

// 可以從 /select 頁面帶 query string，例如 ?target=自己&time=一個月後
const route = useRoute();
const target = route.query.target || "自己";
const time = route.query.time || "一個月後";

const label = `${time}嘅${target}`;
const message = ref("");

const submit = () => {
  alert(`你寫咗：「${message.value}」，會寄俾 ${label}`);
  // 這裡可以加 localStorage 儲存、或發送 API
};
</script>

<script setup lang="ts">
import { ref } from "vue";

const now = new Date(); // 現在日時
const nowStr = now.toLocaleTimeString();
let timeStr = nowStr; // 現在時刻文字列をテンプレート変数として用意
const timeStrRef = ref(nowStr);

function changeTime(): void {
  // 新しい時刻に変更する関数
  const newTime = new Date();
  const newTimeStr = newTime.toLocaleTimeString();
  timeStr = newTimeStr;
  timeStrRef.value = newTimeStr;
}

setInterval(changeTime, 1000);
</script>

<template>
  <p>現在時刻: {{ timeStr }}</p>
  <p>現在時刻(ref): {{ timeStrRef }}</p>
</template>

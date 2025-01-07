<template>
  <button v-if="isVisible" class="back-to-top" @click="scrollToTop">↑</button>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

// 控制按钮显示的状态
const isVisible = ref(false);

// 监听滚动事件来判断按钮显示
const handleScroll = () => {
  isVisible.value = window.scrollY > 200; // 如果滚动超过200px就显示按钮
};

// 滚动回顶部
const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: "smooth" });
};

// 生命周期钩子，添加和清理滚动事件监听
onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<style lang="scss" scoped>
@import "../assets/scss/color.scss";
.back-to-top {
  position: sticky;
  bottom: 40px;
  //   margin-bottom: 20px;
  //   margin-top: -60px;
  //   right: 20px;
  left: 90vw;
  background-color: #ffffff;
  color: $text_color_main;
  border: none;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  font-size: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: 0.3s ease;
}

.back-to-top:hover {
  transform: scale(1.1);
}

.back-to-top:focus {
  outline: none;
}
</style>

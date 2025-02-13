<template>
  <div class="skill-item" @mouseenter="showContext" @mouseleave="hideContext">
    <!-- Icon có animation xoay -->
    <div class="icon-wrapper" :class="{ 'rotate-animation': isHovered }">
      <Icon :icon="icon" :width="64" />
    </div>

    <!-- Thông tin hiển thị khi hover -->
    <transition name="fade">
      <div v-if="isHovered" class="info-box">
        <p class="name">{{ name }}</p>
        <p class="description">{{ description }}</p>
      </div>
    </transition>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Icon } from '@iconify/vue'

defineProps({
  icon: { type: String, required: true },
  name: { type: String, required: true },
  description: { type: String, required: true },
})

const isHovered = ref(false)

const showContext = () => (isHovered.value = true)
const hideContext = () => (isHovered.value = false)
</script>

<style scoped>
.skill-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 12px;
  cursor: pointer;
  position: relative;
  width: 80px; /* Giới hạn kích thước icon */
  text-align: center;
}

.icon-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 64px;
  height: 64px;
  transition: transform 0.3s ease;
}

/* Hover vào thì xoay icon */
.rotate-animation {
  transform: rotate(360deg);
}

.info-box {
  position: absolute;
  bottom: 100%;
  left: 50%;
  transform: translateX(-50%);
  background: white;
  padding: 8px 12px;
  border-radius: 6px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  width: 270px; /* Giới hạn kích thước box */
  z-index: 10;
  word-wrap: break-word;
  white-space: normal; /* Cho phép text xuống dòng */
}

.name {
  font-size: 14px;
  font-weight: bold;
  color: #333;
}

.description {
  font-size: 12px;
  color: #666;
}

/* Animation khi hover */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>

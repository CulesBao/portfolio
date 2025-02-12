<script setup>
import { socialLinks } from '@/data/socialLinks'
import { ref } from 'vue'

const socialLinksRef = ref(socialLinks)
</script>
<template>
  <div class="flex justify-between items-center h-16 bg-gray-800 text-white p-4">
    <div class="left">
      <p class="text-[12px] opacity-50">&copy; Bao Cules: All right reserved.</p>
    </div>
    <div class="mid">
      <div class="flex space-x-4">
        <el-button
          v-for="link in socialLinksRef"
          :key="link.name"
          type="info"
          link="true"
          size="default"
          plain
          @click="() => openLink(link.link)"
        >
          <component :is="link.icon" class="mr-2" />
        </el-button>
      </div>
    </div>
    <div class="right">
      <p class="text-sm ">Made with ❤️ by Bao Cules</p>
    </div>
  </div>
</template>

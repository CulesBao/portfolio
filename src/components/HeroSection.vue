<script setup>
import { ElButton } from 'element-plus'
import { socialLinks } from '@/data/socialLinks'
import { ref } from 'vue'
const socialLinksRef = ref(socialLinks)
const openLink = (url) => {
  if (typeof window !== 'undefined') {
    window.open(url, '_blank', 'noopener,noreferrer')
  } else {
    console.error('window is not defined')
  }
}
</script>
<template>
  <div class="flex flex-row items-center justify-center h-screen">
    <div class="flex flex-col items-center justify-center w-full">
      <div class="my-info">
        <div class="grettings p-4">
          <h1 class="text-xl opacity-70">Hi, I am</h1>
          <h1 class="text-9xl font-bold">Bao</h1>
          <h1 class="text-9xl font-bold">Cules</h1>
          <h1 class="text-xl opacity-70">A Backend Developer</h1>
        </div>
        <div class="my-resume p-4">
          <el-button
            type="info"
            plain
            @click="
              () =>
                openLink(
                  'https://drive.google.com/file/d/1l_0551PUtzJJoP9AWTcLe5-IEwBuqD_q/view?usp=sharing',
                )
            "
          >
            My Resume
          </el-button>
        </div>
        <div class="social-link p-4">
          <div class="flex space-x-4">
            <el-button
              v-for="link in socialLinksRef"
              :key="link.name"
              type="info"
              size="default"
              plain
              :hover="temp"
              @click="() => openLink(link.link)"
            >
              <component :is="link.icon" class="mr-2" />
            </el-button>
          </div>
        </div>
      </div>
    </div>
    <div class="flex items-center justify-center w-full">
      <div class="my-image">
        <img src="@/assets/epl.jpg" alt="my-image" class="rounded-full w-80 h-80 " />
      </div>
    </div>
  </div>
</template>

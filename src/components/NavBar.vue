<script setup>
import { ElAvatar } from 'element-plus'
import { reactive } from 'vue'
import avatarSrc from '@/assets/epl.jpg'

const menu = reactive([
  { name: 'Home', path: '/' },
  { name: 'About', path: '/' },
  { name: 'Skills', path: '/' },
  { name: 'Projects', path: '/' },
  { name: 'Contact', path: '/' },
])
</script>
<template>
  <div
    class="flex justify-between items-center p-4 bg-transparent text-white shadow-md sticky top-0 z-50  "
  >
    <div class="flex items-center justify-between">
      <div class="flex items-center pr-2">
        <ElAvatar
          shape="circle"
          size="default"
          :src="avatarSrc"
          alt="Avatar"
          fit="scale-down"
        ></ElAvatar>
      </div>
      <h1 class="text-x">Bao Cules</h1>
    </div>
    <div>
      <ul>
        <li v-for="item in menu" :key="item.name" class="inline-block px-4 py-2 hover:bg-gray-700">
          <router-link :to="item.path">{{ item.name }}</router-link>
        </li>
      </ul>
    </div>
  </div>
</template>

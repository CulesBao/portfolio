<script setup>
import { ElAvatar, ElSwitch } from 'element-plus'
import { reactive, ref } from 'vue'
import avatarSrc from '@/assets/epl.png'
import { Moon, Sun } from 'lucide-vue-next'

const menu = reactive([
  { name: 'Home', path: '/' },
  { name: 'About', path: '/' },
  { name: 'Skills', path: '/' },
  { name: 'Projects', path: '/' },
  { name: 'Contact', path: '/' },
])

let darkMode = ref(true)
</script>
<template>
  <div class="flex justify-between items-center p-4 bg-transparent text-white shadow-md">
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
        <li class="inline-block px-4 py-2">
          <el-switch
            v-model="darkMode"
            style="--el-switch-on-color: #34495e; --el-switch-off-color: #f1c40f"
            :active-action-icon="Moon"
            :inactive-action-icon="Sun"
          />
        </li>
      </ul>
    </div>
  </div>
</template>

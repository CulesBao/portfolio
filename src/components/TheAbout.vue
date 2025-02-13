<template>
  <div class="skills-container">
    <ViewSkill
      v-for="(skill, index) in MySkills"
      :key="index"
      :icon="skill.icon"
      :name="skill.name"
      :description="skill.description"
    />
  </div>
</template>

<script setup>
import ViewSkill from './ViewSkill.vue'
import { MySkills } from '@/data/skills'
</script>

<style scoped>
.skills-container {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
  padding: 20px;
}
</style>

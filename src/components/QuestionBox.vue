<script lang="ts" setup>
import UiText from '@/ui/UiText.vue'
interface Props {
  question: string
}

defineProps<Props>()
</script>

<template>
  <div class="question-box">
    <UiText :variant="'title-game'">{{ question }}</UiText>
  </div>
</template>

<style scoped>
.question-box {
  width: 500px;
  height: 200px;
  border-radius: 20px;
  background-color: #fff;
  border: 1px solid black;
  display: flex;
  align-items: center;
  text-align: center;
  max-width: 100%;
}
</style>

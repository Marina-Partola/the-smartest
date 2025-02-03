<script lang="ts" setup>
import UiText from '@/ui/UiText.vue'
import clsx from 'clsx'
interface Props {
  answer: string
  checked: boolean
}

defineProps<Props>()

const emit = defineEmits<{
  (e: 'check'): void
}>()
</script>

<template>
  <button class="answer-box" @click="emit('check')">
    <UiText variant="body-game">{{ answer }}</UiText>
    <div :class="clsx('check-box', checked && 'checked')"></div>
  </button>
</template>

<style scoped>
.answer-box {
  padding: 10px 12px;
  border: 1px solid black;
  border-radius: 12px;
  background-color: #fdda99;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 20px;
}

.check-box {
  width: 20px;
  height: 20px;
  border: 1px solid black;
  border-radius: 50%;
  background-color: #fff;
}

.checked {
  background-color: #67d66a;
}
</style>

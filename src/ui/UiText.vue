<script setup lang="ts">
type TextVariant = 'title-game' | 'body-game'
interface Props {
  variant: TextVariant
}

const tagByVariant: Record<TextVariant, string> = {
  'title-game': 'h1',
  'body-game': 'span',
}

defineProps<Props>()
</script>

<template>
  <component :is="tagByVariant[variant]" :class="variant"><slot /></component>
</template>

<style scoped>
.title-game {
  font-size: 32px;
  font-family: 'Montserrat Alternates';
}

.body-game {
  font-size: 24px;
  font-family: 'Montserrat Alternates';
}
</style>

<script setup lang="ts">
import AnswerBox from '@/components/AnswerBox.vue'
import QuestionBox from '@/components/QuestionBox.vue'
import { ref } from 'vue'

const question = ref({
  question: 'Как называется река, которая вытекает из Байкала?',
  answers: [
    {
      answer: 'Ангара',
      checked: false,
    },
    {
      answer: 'Енисей',
      checked: false,
    },
  ],
})

const handleCheck = (index: number) => {
  question.value.answers.forEach((ans, i) => {
    ans.checked = i === index // Выбираем только один вариант
  })
}
</script>

<template>
  <div class="game-view">
    <QuestionBox :question="question.question" />

    <div class="answers">
      <AnswerBox
        v-for="(answer, index) in question.answers"
        :key="answer.answer"
        :answer="answer.answer"
        :checked="answer.checked"
        @check="handleCheck(index)"
      />
    </div>
  </div>
</template>

<style scoped>
.game-view {
  height: 100%;
  background-image: url('../assets/images/background.jpg');
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  background-size: cover;
}

.answers {
  padding: 20px;
  border-radius: 20px;
  background-color: #fff;
  border: 1px solid black;
  display: flex;
  gap: 20px;
  justify-content: space-between;
  width: 500px;
}
</style>

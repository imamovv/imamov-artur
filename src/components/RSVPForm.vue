<template>
  <section id="rsvp" class="rsvp reveal">
    <h2>Подтвердите участие</h2>
    <form @submit.prevent="submit">
      <input v-model="name" type="text" placeholder="Ваше имя" required />
      <div class="attendance">
        <label><input type="radio" v-model="attendance" value="Да" /> Да</label>
        <label><input type="radio" v-model="attendance" value="Нет" /> Нет</label>
      </div>
      <button type="submit">Отправить</button>
    </form>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const name = ref('')
const attendance = ref('')

// const submit = () => {
//   alert(Спасибо, ${name.value}! Ваш ответ: ${attendance.value});
// };
</script>

<style scoped>
.rsvp {
  text-align: center;
  padding: 4rem 2rem 2rem;
}

form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  max-width: 400px;
  margin: 0 auto;
}

input[type='text'] {
  padding: 0.5rem;
}

button {
  background-color: #8b0000;
  color: white;
  padding: 0.5rem;
  border: none;
  cursor: pointer;
  border-radius: 8px;
}

.attendance {
  display: flex;
  gap: 1rem;
}

@media (max-width: 600px) {
  .rsvp {
    padding: 2rem 1rem;
  }

  .attendance {
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>

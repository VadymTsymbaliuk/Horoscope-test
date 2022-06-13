<template>
  <div>
    <div class="progress-bar__container" v-if="answerCollection.length>0">
      <progress :value="answerCollection.length" max="5"></progress>
    </div>
    <section class="poll__container" v-for="(question, index) in questions" :key="index">
      <div v-show="index === questionIndex">
        <h2>{{ question.text }}</h2>
        <ol class="form-group__container">
          <li class="form-group" v-for="(response, index) of question.responses" :key="index">
            <input type="radio"
                   :id="response.id"
                   name="question"
                   v-model="answer"
                   :value="response.value"
            >
            <label :for="response.id">{{ response.value }}</label>
          </li>
        </ol>
        <div class="form-button__container" v-if="answer">
          <button @click="registerAnswers">Далее</button>
        </div>
      </div>
    </section>
  </div>
</template>
<script>

export default {
  name: "VPoll",

  data: () => ({
    questions: [
      {
        text: "Укажите свой пол:",
        responses: [{
          id: "first",
          value: "Женщина"
        }, {
          id: "second",
          value: "Мужчина"
        }]
      },
      {
        text: "В какое время суток Вы чувствуете себя наиболее комфортно?",
        responses: [
          {
            id: "first",
            value: "Утро"
          }, {
            id: "second",
            value: "Обед"
          }, {
            id: "third",
            value: "Вечер"
          },
          {
            id: "fourth",
            value: "Ночь"
          }]
      },
      {
        text: "Подскажите, мучает ли Вас бессонница последнее время?",
        responses: [
          {
            id: "first",
            value: "Да"
          }, {
            id: "second",
            value: "Нет"
          }, {
            id: "third",
            value: "Иногда"
          }
        ]
      },
      {
        text: "Чувствуете ли Вы в последнее время, что вам никак не удается осуществить ваши планы?",
        responses: [
          {
            id: "first",
            value: "Да"
          }, {
            id: "second",
            value: "Нет"
          }, {
            id: "third",
            value: "Иногда"
          }
        ]
      },
      {
        text: "Какой Вы видите свою жизнь через 5 лет?",
        responses: [
          {
            id: "first",
            value: "Брак, семья, дети, дом"
          }, {
            id: "second",
            value: "Путешествия по Миру"
          }, {
            id: "third",
            value: "Успешная карьера"
          }, {
            id: "fourth",
            value: "Всё вместе"
          }
        ]
      }
    ],
    questionIndex: 0,
    answer: "",
    answerCollection: []
  }),
  methods: {
    registerAnswers() {
      this.answerCollection.push(this.answer)
      this.questionIndex++
      this.$emit('hideHeadSection')
      console.log(this.answerCollection)
    }
  }

}
</script>

<style scoped>

</style>
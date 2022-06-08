<template>
  <section class="poll__container">
    <h2>Укажите свой пол:</h2>
    <form @submit.prevent>
      <div class="form-group__container" v-for="(question,index) of questions" :key="index" v-if="index >= answers.length ? index : false">
        <div class="form-group" v-for="item of question" :key="item">
          <input type="radio" :id="item.sex" :value="item.sex" name="question" v-model="form">
          <label :for="item.sex">{{ item.value }}</label>
        </div>
      </div>
      <div class="form-button__container">
        <button @click="registerAnswers" v-if="available">Далее</button>
      </div>
    </form>
  </section>
</template>

<script>

export default {
  name: "VPoll",

  data: () => ({
    form: "",
    questions: [
      [{
        sex: "female",
        value: "Женщина"
      }, {
        timeOfDay: "morning",
        value: "Утро"
      }],
      [{
        timeOfDay: "morning",
        value: "Утро"
      }, {
        timeOfDay: "morning",
        value: "Утро"
      },{
        timeOfDay: "morning",
        value: "Утро"
      }]
    ],
    answers: [],
    available: false
  }),
  methods: {
    registerAnswers() {
      this.answers.push(this.form)
    }
  },
  watch: {
    form: function () {
      this.available = true
    }
  }
}
</script>

<style scoped>

</style>
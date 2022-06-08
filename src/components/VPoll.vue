<template>
  <section class="poll__container">
    <h2>Укажите свой пол:</h2>
    <form @submit.prevent>
      <div class="form-group__container">
        <div class="form-group">
          <input type="radio" id="female" value="female" name="question" v-model="form">
          <label for="female">Женщина</label>
        </div>
        <div class="form-group">
          <input type="radio" id="male" value="male" name="question" v-model="form">
          <label for="male">Мужчина</label>
        </div>
      </div>
      <div class="form-button__container" >
        <button @click="registerAnswers" v-if="available" >Далее</button>
      </div>
    </form>
  </section>
</template>

<script>

export default {
  name: "VPoll",

  data:()=>({
    form:"",
    answers:[],
    available: false
  }),
  methods:{
    registerAnswers(){
      this.answers.push(this.form)
    }
  },
  watch:{
    form:function (){
      this.available = true
    }
  }
}
</script>

<style scoped>

</style>
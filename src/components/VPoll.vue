<template>
  <section>
    <h2>Укажите свой пол:</h2>
    <form>
      <input type="radio" id="female" value="female" name="sex">
      <label for="female">Женщина </label>
      <input type="radio" id="male" value="male" name="sex">
      <label for="male">Мужчина</label>
    </form>
  </section>
</template>

<script>
export default {
  name: "VPoll"
}
</script>

<style scoped>

</style>
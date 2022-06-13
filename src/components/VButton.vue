<template>
  <div>
    <button @click="enlargeText">
      Увеличить размер текста
    </button>
  </div>
</template>

<script>
export default {
  name: "Button",
  data:()=>({
    information:'aaa'
  }),
  methods:{
    enlargeText(){

      this.$emit('testMethod',{
        information: this.information
      })
      console.log("method")
    }
  }

}
</script>

<style scoped>


</style>
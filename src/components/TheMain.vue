<template>
  <main>
    <div class="container">
      <section v-if="showHeadSection" >
        <div class="img-container">
          <img src="../assets/images/sec_animated_circle.png" alt="animated">
        </div>
        <div class="text__container" :style="{fontSize: postFontSize + 'em'}" >
          <h2>
            Узнайте, как 2021 год изменит жизнь каждого из нас!
          </h2>
          <p>К сожалению, 2020 год принес нам немало неприятностей, даже откровенных проблем и несчастий. Не смотря на
            это, 3 знака зодиака очень скоро обретут долгожданное счастье! 2021 год затронет своими потрясениями каждого
            из нас.</p>
        </div>
      </section>
      <VPoll @hideHeadSection="showHeadSection = false"/>
      <VDateOfBirdth />
    </div>
  </main>
</template>

<script>

import VPoll from "@/components/VPoll";
import VButton from "@/components/VButton";
import VDateOfBirdth from "@/components/VDateOfBirdth";

export default {
  name: "Main",
  components: { VPoll, VButton, VDateOfBirdth},
  data:()=>({
    showHeadSection: true,
    postFontSize: 1,
  }),
  methods:{
    showInformation(data){
      console.log(" child component said login", data)
    }
  }
}
</script>

<style scoped>


</style>
<template>
  <main>
    <div class="container">
      <section>
        <div class="img-container">
          <img src="../assets/images/sec_animated_circle.png" alt="animated">
        </div>
        <div class="text__container">
          <h2>
            Узнайте, как 2021 год изменит жизнь каждого из нас!
          </h2>
          <p>К сожалению, 2020 год принес нам немало неприятностей, даже откровенных проблем и несчастий. Не смотря на
            это, 3 знака зодиака очень скоро обретут долгожданное счастье! 2021 год затронет своими потрясениями каждого
            из нас.</p>
        </div>
        <VPoll/>
        <VButton/>
      </section>
    </div>
  </main>
</template>

<script>
import VButton from "@/components/VButton";
import VPoll from "@/components/VPoll";

export default {
  name: "Main",
  components: {VButton, VPoll}
}
</script>

<style scoped>


</style>
<template>
  <div id="app">
    <TheHeader/>
    <TheMain/>
    <TheFooter/>
  </div>
</template>

<script>
import TheMain from "@/components/TheMain";
import TheHeader from "@/components/TheHeading";
import TheFooter from "@/components/TheFooter";

export default {
  name: 'App',
  components: {
    TheMain, TheHeader, TheFooter
  }
}
</script>

<style>
</style>

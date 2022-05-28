<template>
  <Advice
    :advice-number="number"
    :advice-text="advice"
    @new-advice="getAdvice()"
  />
</template>

<script>
import Advice from "@/components/Advice.vue";
export default {
  components: {
    Advice,
  },
  data() {
    return {
      number: "000",
      advice: "Click the dice below for advice.",
    };
  },
  methods: {
    async getAdvice() {
      const res = await fetch("https://api.adviceslip.com/advice");
      const results = await res.json();
      this.number = results.slip.id;
      this.advice = results.slip.advice;
    },
  },
};
</script>

<style>
@import "@/components/base.css";
@import url("https://fonts.googleapis.com/css2?family=Manrope:wght@800&display=swap");

#app {
  scroll-behavior: smooth;
}
</style>

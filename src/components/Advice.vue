<template>
  <div class="container">
    <div class="advice">
      <p class="neon">ADVICE #{{ adviceNumber }}</p>
    </div>
    <div class="txt">
      <p>{{ adviceText }}</p>
      <img
        id="desktop"
        src="@/assets/images/pattern-divider-desktop.png"
        alt=""
      />
      <img
        id="mobile"
        src="@/assets/images/pattern-divider-mobile.png"
        alt=""
      />
      <div>
        <button @click="$emit('newAdvice')">
          <img id="dice" src="@/assets/icons/icon-dice.png" alt="" />
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Advice",
  props: {
    adviceNumber: String,
    adviceText: String,
  },
};
</script>

<style>
#mobile {
  display: none;
}
.container {
  /*Align Center Vertically AND Horizontally */
  margin: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);

  padding: 40px;
  width: 450px;
  background: var(--bs-dark-graish-blue);
  border-radius: 16px;
  text-align: center;
}
.advice p {
  font-size: smaller;
  letter-spacing: 4px;
}
button {
  margin: 40px 0 0 0;
  background: transparent;
  border-style: none;
  cursor: pointer;
}
#dice {
  width: 70px;
}

@media only screen and (max-width: 600px) {
  .container {
    width: 70%;
  }
  #mobile {
    display: initial;
  }
  #desktop {
    display: none;
  }
}
</style>

<template>
  <div class="container">
    <heart class="heart-container"></heart>
    <h2 style="color: #fff; font-size: 30px; padding-top: 20px">Gute Nacht mein Schatz!</h2>
    <h2 style="color: #fff; font-size: 30px; padding-top: 20px">Ich hab dich lieb so wie du bist egal wie gestresst du bist!</h2>
    <h2 style="color: #fff; font-size: 30px; padding-top: 20px">Ich wünsch dir eine schöne Nacht! Schlaf gut! Bussi!</h2>
  </div>
</template>

<script>
import Heart from "~/components/Heart"

export default {
  components: {
    Heart
  }
};
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  height: 100vh;

  padding: 2rem;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  text-align: center;
}

.heart-container{
  width: 100vw;
  /* height: 100vh; */
}
</style>

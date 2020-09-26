<template>
  <div class="container">
    <celebration class="celebration-container"></celebration>
    <h2 style="color: #333; font-size: 25px; padding-top: 20px">
      Lieber Papa!
    </h2>
    <h2 style="color: #333; font-size: 25px; padding-top: 20px">
      Ich wünsche dir alles Gute zu deinem 55. Geburtstag.
    </h2>
    <h2 style="color: #333; font-size: 25px; padding-top: 20px">
      Ich finde es sehr schade, dass ich heute nicht bei dir sein kann. Ich
      hoffe wir können ihn bald nachfeiern und eventuell auch wieder gemeinsam
      frühstücken 😃
    </h2>
    <h2 style="color: #333; font-size: 25px; padding-top: 20px">
      Magdalena und ich freuen schon sehr, wenn du uns in München besuchen
      kommst.
    </h2>
    <h2 style="color: #333; font-size: 25px; padding-top: 20px">
      Ich freue mich, dass du mein Papa bist und ich immer auf dich zählen kann!
    </h2>
    <h2 style="color: #333; font-size: 25px; padding-top: 20px">
      Liebe Grüße <br />
      Thomas
    </h2>

    <h2 style="color: #333; font-size: 25px; padding-top: 20px">
      PS: Wir haben noch eine kleine Überraschung für dich vorbereitet. Schalte einfach den Ton ein und drück auf "Play" 😁	
    </h2>
    <audio ref="audio" src="/LandingPage/happy_birthday_papa.wav" preload loop></audio>
    <button class="button" @click="buttonClick">{{ buttonName }}</button>
  </div>
</template>

<script>
import Celebration from "~/components/Celebration";

export default {
  data() {
    return {
      buttonState: "Not Started",
      buttonName: "Play",
    };
  },
  components: {
    Celebration,
  },
  methods: {
    buttonClick() {
      console.log(this.buttonState);
      switch (this.buttonState) {
        case "Not Started":
        case "Paused":
          this.$refs.audio.play();
          this.buttonState = "Playing";
          this.buttonName = "Pause";
          break;
        case "Playing":
          this.$refs.audio.pause();
          this.buttonState = "Paused";
          this.buttonName = "Play";
          break;
      }
    },
  },
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
  min-height: 100vh;

  padding: 2rem;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  text-align: center;
}

.heart-container {
  width: 100vw;
  /* height: 100vh; */
}

.celebration-container {
  margin: 0 auto;
  max-width: 15rem;
  max-height: 15rem;
  margin-bottom: 2.5rem;
}

.button {
  font-size: 1.5rem;
  margin-top: 2rem;
  color: #333;
  border: 2px solid #333;
  border-radius: 1.4rem;
  padding: 0.4rem 1rem;
}

.button:hover {
  color: #eee;
  background-color: #333;
}

.button:focus,
.button:active {
  outline: none;
}
</style>

<template>
  <div class="container">
    <celebration v-if="matched" class="celebration-container"></celebration>
    <h2 v-if="matched" class="block text-gray-500 font-bold md:text-right mb-1 md:mb-0 pr-4">00340434284244534532</h2>
    <h2 v-if="matched" class="block text-gray-500 font-bold md:text-right mb-1 md:mb-0 pr-4">Lieber Flo! Du bist uns schon auf den Fersen ;)</h2>
    <h2 v-if="matched" class="block text-gray-500 font-bold md:text-right mb-1 md:mb-0 pr-4">Gib diesen Code auf der Webseite von einem 1969 in San Francisco gegründeten Unternehmens ein.</h2>
    <div style="diplay: flex; justify-content: center; align-items: center">
      <input
        v-if="!matched"
        v-model="input_text"
        class="
          bg-gray-200
          appearance-none
          border-2 border-gray-200
          rounded
          py-2
          px-4
          text-gray-700
          leading-tight
          focus:outline-none focus:bg-white focus:border-purple-500
        "
      />
      <button
        v-if="!matched"
        class="
          shadow
          bg-purple-500
          hover:bg-purple-400
          focus:shadow-outline focus:outline-none
          text-white
          font-bold
          py-2
          px-4
          rounded
        "
        @click="buttonClick"
      >
        {{ buttonName }}
      </button>
    </div>
  </div>
</template>

<script>
import Celebration from "~/components/Celebration";

export default {
  data() {
    return {
      buttonState: "Not Started",
      buttonName: "Enter",
      matched: false,
      input_text: "",
    };
  },
  components: {
    Celebration,
  },
  methods: {
    buttonClick() {
      if (this.input_text === "22304591") {
        this.matched = true;
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

.input-field {
  outline: #333;
  border: 1px solid #333;
  margin-right: 5rem;
}
</style>

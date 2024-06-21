<script setup lang="ts">
import nuxtLogo from "~/assets/images/nuxt.png";
import wailsLogo from "~/assets/images/logo-universal.png";
import { Greet } from "~/wailsjs/go/main/App";

const name = ref<string>("");
const greeting = ref<string>("\xa0");

async function greet() {
  greeting.value = await Greet(name.value);
}
</script>
<template>
  <div class="full-screen-container">
    <div class="screen-centered-card-wrapper">
      <div class="screen-centered-card">
        <div class="logos">
          <img :src="wailsLogo" style="height: 100%" />
          <img :src="nuxtLogo" style="height: 50%" />
        </div>
        <div>
          <h1>Welcome to Wails + Nuxt</h1>
        </div>
        <div class="text-center">
          {{ greeting }}
        </div>
        <div class="greeter">
          <input
            v-model="name"
            type="text"
            placeholder="Your name..."
            class="input greeter-input"
          />
          <button class="btn greeter-button" @click="greet">Greet</button>
        </div>
        <div>
          <button class="btn" @click="Quit()">Close App</button>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.btn {
  all: unset;
  box-sizing: border-box;
  width: 100%;
  padding: 0.5rem;
  background: #333;
  text-align: center;
  transition: 0.25s;
  border-radius: 0.25rem;
}
.btn:hover {
  background: #444;
  transition: 0.25s;
}
.input {
  all: unset;
  box-sizing: border-box;
  padding: 0.5rem;
  border-radius: 0.25rem;
  background: #222;
}
.text-center {
  text-align: center;
}
.full-screen-container {
  height: 100%;
  display: flex;
  flex-direction: column;
}
.screen-centered-card-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  flex-grow: 1;
}
.screen-centered-card {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.logos {
  height: 6rem;
  display: flex;
  flex-direction: row;
  gap: 1rem;
  place-items: center;
  justify-content: space-evenly;
}
.greeter {
  display: flex;
  flex-direction: row;
  gap: 1rem;
}
.greeter-input {
  flex-basis: 75%;
}
.greeter-button {
  flex-basis: 25%;
}
</style>

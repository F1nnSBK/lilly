<template>
  <div class="wrapper">
    <div class="form-wrapper">
      <div class="form-container">
        <h3>Wer ist das schönste und einzige Mädchen?</h3>
        <div class="btn-container">
          <button type="button" @click="clickedGirlName('Lucy')" class="btn">
            Lucy
          </button>
          <button type="button" @click="clickedGirlName('Amelie')" class="btn">
            Amelie
          </button>
          <button type="button" @click="clickedGirlName('Sarah')" class="btn">
            Sarah
          </button>
          <button
            type="button"
            @click="clickedGirlName('Lilly')"
            id="lillyBtn"
            class="btn"
          >
            Lilly
          </button>
          <button type="button" @click="clickedGirlName('Jenni')" class="btn">
            Jenni
          </button>
          <button type="button" @click="clickedGirlName('Yusuf')" class="btn">
            Yusuf
          </button>
          <button type="button" @click="clickedGirlName('Elena')" class="btn">
            Elena
          </button>
          <button type="button" @click="clickedGirlName('Mara')" class="btn">
            Mara
          </button>
        </div>
      </div>
    </div>

    <img
      ref="happyGif"
      id="happyGif"
      src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExaXZvanYyaG50bHB5a29yM2htbmtvMGF0cTgwNzhpMjBmcmNheTk0ZyZlcD12MV9naWZzX3NlYXJjaCZjdD1n/MDJ9IbxxvDUQM/giphy.gif"
      alt="happyGif"
    />
    <img
      ref="angryGif"
      id="angryGif"
      src="https://media1.tenor.com/m/O7_ZgFSBGZIAAAAd/angry-cat-sour-cat.gif"
      alt="angryCat"
    />
  </div>
</template>

<style scoped>
* {
  margin: 0;
}

#happyGif {
  display: none;
  position: fixed;
  width: 120%;
}

#angryGif {
  display: none;
  position: fixed;
}

.wrapper {
  height: 100dvh;
  background-color: pink;
  display: flex;
  align-items: center;
  justify-content: center;
  color: black;
  width: 100%;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

.form-wrapper {
  background-color: white;
  padding: 2rem;
  border-radius: 20px;
  box-shadow: 8px 8px black;
}

.btn {
  padding: 0.5rem 2rem;
  background-color: blanchedalmond;
  border: 2px solid gray;
  border-radius: 15px;
  color: black;
}

@media screen and (min-width: 760px) {
  .btn-container {
    display: flex;
    flex-direction: row;
  }

  .form-wrapper {
    width: fit-content;
  }

  .btn {
    margin: 1rem 0.5rem 1rem 0.5rem;
  }

  #angryGif {
    width: 80%;
  }
}

@media screen and (max-width: 760px) {
  .btn-container {
    display: flex;
    flex-direction: column;
  }

  .form-wrapper {
    width: 60%;
    height: fit-content;
  }

  .btn {
    margin: 0.25rem 0.5rem 0.25rem 0.5rem;
  }

  #angryGif {
    width: 100%;
  }
}
</style>

<script setup>
import { ref } from "vue";

const happyGif = ref(null);
const angryGif = ref(null);

function clickedGirlName(clickedName) {
  const clickedButton = event.target;

  if (clickedName !== "Lilly") {
    console.log("Bist du dumm?");
    clickedButton.style.cursor = "default";
    clickedButton.style.pointerEvents = "none";
    clickedButton.style.color = "lightgray";
    clickedButton.style.backgroundColor = "gray";

    angryGif.value.style.display = "block";
    setTimeout(() => {
      angryGif.value.style.display = "none";
    }, 2000);
  } else {
    console.log("Yay!");
    happyGif.value.style.display = "block";
  }
}

definePageMeta({
  title: "Lilly <3",
});
</script>

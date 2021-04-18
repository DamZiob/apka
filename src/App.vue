<template>
  <div id="app">
    <b-container>
      <b-row>
        <b-col class="menu" cols="6" offset="3">
          <div class="name">Perkusja</div>
          <label class="vol" for="range-1">Volume</label>
    <b-form-input id="range-1" v-model="value" type="range" min="0" max="5"></b-form-input>
        </b-col>
        <b-col class="col" cols="3" offset="3">
          <div class="section">
            <div
              class="button btnFirst"
              v-for="snare in snares"
              :key="snare.id"
              @click="playSnares(snare.url)">
              {{ snare.id }}
            </div>
          </div>
        </b-col>
        <b-col class="col" cols="3" offset="0">
          <div class="section">
            <div
              class="button btnSecond"
              v-for="bass in basses"
              :key="bass.id"
              @click="playBasses(bass.url)">
              {{ bass.id }}
            </div>
          </div>
        </b-col>
        <b-col class="col second" cols="3" offset="3">
          <div class="section">
            <div
              class="button btnThird "
              v-for="hihat in hihats"
              :key="hihat.id"
              @click="playHihats(hihat.url)">
              {{ hihat.id }}
            </div>
          </div>
        </b-col>
        <b-col class="col second" cols="3" offset="0">
          <div class="section">
            <div
              class="button btnFourth"
              v-for="waterdrum in waterdrums"
              :key="waterdrum.id"
              @click="playWaterdrums(waterdrum.url)">
              {{ waterdrum.id }}
            </div>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import waterdrums from "./store/waterDrums";
import snares from "./store/snares";
import basses from "./store/basses";
import hihats from "./store/hiHats";

export default {
  name: "App",
  components: {},
  data() {
    return {
      waterdrums,
      snares,
      basses,
      hihats,
      value:3
    };
  },
  methods: {
    playSnares(snares) {
      let audio = new Audio(snares);
      audio.volume=this.value /5;
      audio.play();
    },
    playBasses(basses) {
      let audio = new Audio(basses);
      audio.volume=this.value /5;
      audio.play();
    },
    playHihats(hihats) {
      let audio = new Audio(hihats);
     audio.volume=this.value /5;
      audio.play();
    },
    playWaterdrums(waterdrums) {
      let audio = new Audio(waterdrums);
      audio.volume=this.value /5;
      audio.play();
      
    },
  },
};
</script>

<style >
@import "./App.css";
</style>

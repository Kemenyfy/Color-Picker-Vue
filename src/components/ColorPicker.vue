<template>
  <div class="App">
    <header class="App-Header">
      <header class="App-Title-1">A Pretty Useful</header>
      <header class="App-Title-2" :style="titleStyle">Color Picker</header>
      <header class="App-Title-3">Created by Somebody/Somehow/Maybe</header>
    </header>
    <section>
      <section class="Main-Picker">
        <div class="ColorBox" :style="boxStyle" >  
        </div>
          <section class="Sliders">
            <div class="Captions">Hue</div>
            <input 
              type="range" 
              min="0" 
              max="360"
              v-on:input="this.updateHueValue"
              :value="this.hue" />
            <div class="Captions">Saturation</div>
            <input 
              type="range"
              min="0" 
              max="100"
              v-on:input="updateSaturationValue"
              :value="this.saturation" />
            <div class="Captions">Lightness</div>
            <input 
              type="range" 
              min="0" 
              max="100"
              v-on:input="updateLightnessValue"
              :value="this.lightness" />
            <div class="Captions">Alpha</div>
            <input 
              type="range" 
              min="0" 
              max="100"
              v-on:input="updateAlphaValue"
              :value="this.alpha" />
          </section>
      </section>
    <section>
      <input class="ColorInputs" placeholder="Color Hex" type="text"/>
    </section>  
    </section>
  </div>
</template>

<script>
export default {
  name: "ColorPicker",
  data: function() {
    return {
      hue: 180,
      saturation: 50,
      lightness: 50,
      alpha: 100
    }
  },
  methods: {
    updateHueValue: function (event){
      return this.hue = event.target.value
    },
    updateSaturationValue: function (event){
      return this.saturation = event.target.value
    },
    updateLightnessValue: function (event){
      return this.lightness = event.target.value
    },
    updateAlphaValue: function (event){
      return this.alpha = event.target.value
    }
  },
  computed: {
    newAlpha: function () {
      return this.alpha / 100
    },
    boxStyle: function() {
      return {
        "background-color": "hsla(" + this.hue + ", " + this.saturation + "%, " + this.lightness + "%, " + this.newAlpha + " )",
      };},
    titleStyle: function() {
      return {
        "color": "hsla(" + this.hue + ", " + this.saturation + "%, " + this.lightness + "%, " + this.newAlpha + " )",
      };}
  },
};
</script>

<style scoped>
.App {
  text-align: center;
}

.App-Header {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  background-color: #222;
  color: white;
  margin-bottom: 1em;
  padding: 1em;
}

.App-Title-1 {
  font-size: 1.5em;
}

.App-Title-2 {
  font-size: 3em;
  padding: 0.2em;
}

.App-Title-3 {
  font-size: 0.7em;
}

.ColorBox {
  background-color: black;
  height: 9em;
  width: 7em;
  border-radius: 6px;
}

.Captions {
  font-size: 0.5em;
}
.Main-Picker {
  display: flex;
  justify-content: center;
}

.Sliders {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 8px;
}

input {
  text-align: center;
  margin-bottom: 0.5em;
}

.ColorInputs {
  margin-top: 0.8em;
}
</style>

<template>
  <div class="App">
    <header class="App-Header">
      <header class="App-Title-1">A Pretty Useful</header>
      <header class="App-Title-2">Color Picker</header>
      <header class="App-Title-3">Created by Somebody/Somehow/Maybe</header>
    </header>
    <section>
      <section class="Main-Picker">
        <div class="ColorBox" style="currentStyle"></div>
          <section class="Sliders">
            <div class="Captions">Hue</div>
            <input 
              type="range" 
              min="0" 
              max="360" 
              valueName="hue" 
              v-model="value"
              v-on:input="updateValue()" />
            <div class="Captions">Saturation</div>
            <input 
              type="range"
              min="0" 
              max="100"
              valueName="saturation" 
              :value="saturation"
              v-on:input="updateValue()" />
            <div class="Captions">Lightness</div>
            <input 
              type="range" 
              min="0" 
              max="100" 
              valueName="lightness"
              :value="lightness" 
              v-on:input="updateValue()" />
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
  props: {
    value: Number,
  },
  data: function() {
    return {
      dataValue: this.value,
      hue: 180,
      saturation: 50,
      lightness: 50
    }
  },
  methods: {
    updateValue: function() {
      this.value = parseInt(this.dataValue);
      valueName = this.value
    },
    currentStyle: function () {
      return `backgroundColor: hsla(${this.hue}, ${this.saturation}%, ${this.lightness}%);`
    }
  }
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
  height: 7em;
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

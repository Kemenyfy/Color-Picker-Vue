<template>
  <div class="App">
    <header class="App-Header">
      <h4 class="App-Title-1">A Pretty Useful</h4>
      <h2 class="App-Title-2">Color Picker</h2>
      <h6 class="App-Title-3">Created by Somebody/Somehow/Maybe</h6>
    </header>
    <section>
      <section class="Main-Picker">
        <div class="ColorBox"></div>
          <section class="Sliders">
            <div class="Captions">Hue</div>
            <input type="range" min="0" max="360" onInput={this.updateColor} onChange={this.hueUpdated} value={this.state.hue} />
            <div class="Captions">Saturation</div>
            <input type="range" min="0" max="100" onInput={this.updateColor} onChange={this.saturationUpdated} value={this.state.saturation} />
            <div class="Captions">Lightness</div>
            <input type="range" min="0" max="100" onInput={this.updateColor} onChange={this.lightnessUpdated} value={this.state.lightness} />
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
  name: "Snowman",
  props: {}
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
  padding: .2em;
}

.App-Title-3 {
  font-size: .7em;
}

.ColorBox {
  height: 7em;
  width: 7em;
  border-radius: 6px;
}

.Captions {
  font-size: .5em;
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
  margin-top: .8em;
}
</style>

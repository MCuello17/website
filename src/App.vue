<template>
  <div id="app">
    <span class="cursor"></span>
    <router-view/>
    <span id="overlay"></span>
  </div>
</template>

<style>
@import url('./assets/styles/app.css');
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;1,100;1,200;1,300;1,400;1,500;1,600&display=swap');

* {
  box-sizing: border-box;
  font-family: 'Roboto Mono', monospace;
  font-weight: 700;
  font-size: 20px;
  user-select: none;
}

body {
  margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.cut-corner {
    position: relative;
}

.cut-corner:before {
    position: absolute;
    left: -1px;
    bottom: -1px;
    content: '';
    border-bottom: 70px solid;
    border-color: inherit;
    border-right: 70px solid transparent;
}

.cut-corner:after {
    position: absolute;
    left: -3px;
    bottom: -3px;
    content: '';
    border-bottom: 70px solid var(--background);
    border-right: 70px solid transparent;
}
</style>

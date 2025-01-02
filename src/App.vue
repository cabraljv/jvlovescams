<script setup>
import MainPage from './MainPage.vue'
</script>

<template>
  <main-page></main-page>
</template>

<style>
:root {
  font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  line-height: 1.5;
  font-weight: 400;

  color-scheme: light dark;
  color: rgba(255, 255, 255, 0.87);
  background-color: #242424;

  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}


body {
  margin: 0;
  min-width: 320px;
  min-height: 100vh;
  font-family: "Pixelify Sans", serif;
}


.pixel, .pixel2 {
  font-size: 25px;
  color: white;
  height: auto;
  margin: 10px;
  font-family: 'VT323';
  
  position: relative;
  display: inline-block;
  vertical-align: top;
  text-transform: uppercase;
  
  cursor: pointer;
  
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.pixel:active, .pixel2:active {
  top: 2px;
}

.pixel {
  line-height: 0;
  
  image-rendering: optimizeSpeed;
  image-rendering: -moz-crisp-edges; /* Firefox */
  image-rendering: -o-crisp-edges; /* Opera */
  image-rendering: -webkit-optimize-contrast; /* Webkit (non-standard naming) */
  image-rendering: crisp-edges;
  -ms-interpolation-mode: nearest-neighbor; /* IE (non-standard property) */
  
  border-style: solid;
  border-width: 20px;
  -moz-border-image: url(./assets/button-border.png) 20 stretch;
  -webkit-border-image: url(./assets/button-border.png) 20 stretch;
  -o-border-image: url(./assets/button-border.png) 20 stretch;
  border-image: url(./assets/button-border.png) 20 stretch;
}

.pixel p {
  display: inline-block;
  vertical-align: top;
  position: relative;
  width: auto;
  text-align: center;
  margin: -20px -20px;
  line-height: 20px;
  padding: 10px 20px;
  
	background: #fff;
	background:
		linear-gradient(135deg, transparent 10px, #ff0000 0) top left,
		linear-gradient(225deg, transparent 10px, #ff0000 0) top right,
		linear-gradient(315deg, transparent 10px, #ff0000 0) bottom right,
		linear-gradient(45deg,  transparent 10px, #ff0000 0) bottom left;
	background-size: 50% 50%;
	background-repeat: no-repeat;
	background-image:
		radial-gradient(circle at 0 0, rgba(204,0,0,0) 14px, #ff0000 15px),
		radial-gradient(circle at 100% 0, rgba(204,0,0,0) 14px, #ff0000 15px),
		radial-gradient(circle at 100% 100%, rgba(204,0,0,0) 14px, #ff0000 15px),
		radial-gradient(circle at 0 100%, rgba(204,0,0,0) 14px, #ff0000 15px);
}

.pixel2 {
  position: relative;
  display: block;
  margin: 10px;
  font-family: 'VT323';
  text-transform: uppercase;
  
  font-size: 25px;
  color: white;
}

.pixel2::before {
  content: "";
  display: block;
  position: absolute;
  top: 10px;
  bottom: 10px;
  left: -10px;
  right: -10px;
  background: red;
  z-index: -1;
}

.pixel2::after {
  content: "";
  display: block;
  position: absolute;
  top: 4px;
  bottom: 4px;
  left: -6px;
  right: -6px;
  background: red;
  z-index: -1;
}

.pixel2 {
  padding: 10px 10px;
  position: relative;
  background: red;
  width: auto;
  z-index: 2;
}

.pixel-disabled {
  cursor: not-allowed;
  -moz-border-image: url(./assets/button-border-disabled.png) 20 stretch;
  -webkit-border-image: url(./assets/button-border-disabled.png) 20 stretch;
  -o-border-image: url(./assets/button-border-disabled.png) 20 stretch;
  border-image: url(./assets/button-border-disabled.png) 20 stretch;
}
.pixel-disabled p{
  background:
		linear-gradient(135deg, transparent 10px, #7F7F7F 0) top left,
		linear-gradient(225deg, transparent 10px, #7F7F7F 0) top right,
		linear-gradient(315deg, transparent 10px, #7F7F7F 0) bottom right,
		linear-gradient(45deg,  transparent 10px, #7F7F7F 0) bottom left;
	background-size: 50% 50%;
	background-repeat: no-repeat;
	background-image:
		radial-gradient(circle at 0 0, rgba(204,0,0,0) 14px, #7F7F7F 15px),
		radial-gradient(circle at 100% 0, rgba(204,0,0,0) 14px, #7F7F7F 15px),
		radial-gradient(circle at 100% 100%, rgba(204,0,0,0) 14px, #7F7F7F 15px),
		radial-gradient(circle at 0 100%, rgba(204,0,0,0) 14px, #7F7F7F 15px);
}
</style>

<template>
  <div id="app" class="container">
    <div class="header">
      <p>{{ headerText }}</p>
    </div>
    <div class="main">
      <h1>Rares Andrei </h1>
    </div>
    <div class="buttons">
      <button class="button-64" onclick="location.href='https://www.linkedin.com/in/rares-andrei-herghelegiu-44ab5528a?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app'" role="button"><span class="text">LinkedIn</span></button>
      <NuxtLink to="/about" class="button-65" role="button"><span class="text">About Me</span></NuxtLink>
      <button class="button-66" onclick="location.href='https://github.com/RaresAndrei0'" role="button"><span class="text">Github</span></button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      headerTexts: ["Welcome to my website!", "Written in Vue!", "Nuxt.js included :)", "I hope you enjoy!"],
      currentTextIndex: 0,
      headerText: "Hello!"
    };
  },
  mounted() {
    this.startHeaderTextRotation();
  },
  methods: {
    startHeaderTextRotation() {
      setInterval(() => {
        this.currentTextIndex = (this.currentTextIndex + 1) % this.headerTexts.length;
        this.headerText = this.headerTexts[this.currentTextIndex];
      }, 5000);
    },
    redirect(url) {
      window.location.href = url;
    }
  }
}
</script>

<style>
body {
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: radial-gradient(circle, rgba(20,20,20,1) 0%, rgba(0,0,0,1) 100%);
  color: #fff;
  font-family: Arial, sans-serif;
}

#app {
  text-align: center;
}

.header {
  margin: 0 auto;
  height: 50px;
  top: 20px;
  position: absolute;
  left: 0;
  right: 0;
  text-align: center;
  color: #ccc;
}

.main {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60vh;
}

.main h1 {
  font-size: 4rem;
  font-weight: bold;
  letter-spacing: 0.2rem;
  color: #fff;
  text-shadow: 0 0 20px rgba(0, 0, 255, 0.5);
}

.buttons {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.button-64,
.button-65,
.button-66 {
  align-items: center;
  background-image: linear-gradient(144deg,#AF40FF, #5B42F3 50%,#00DDEB);
  border: 0;
  border-radius: 8px;
  box-shadow: rgba(151, 65, 252, 0.2) 0 15px 30px -5px;
  box-sizing: border-box;
  color: #FFFFFF;
  display: flex;
  font-family: Phantomsans, sans-serif;
  font-size: 20px;
  justify-content: center;
  line-height: 1em;
  max-width: 100%;
  min-width: 140px;
  padding: 3px;
  text-decoration: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  white-space: nowrap;
  cursor: pointer;
  margin: 10px 0;
}

.button-64:active,
.button-64:hover,
.button-65:active,
.button-65:hover,
.button-66:active,
.button-66:hover {
  outline: 0;
}

.button-64 span,
.button-65 span,
.button-66 span {
  background-color: rgb(5, 6, 45);
  padding: 11px 24px;
  border-radius: 6px;
  width: 100%;
  height: 100%;
  transition: 300ms;
}

.button-64:hover span,
.button-65:hover span,
.button-66:hover span {
  background: none;
}

@media (min-width: 768px) {
  .main h1 {
    font-size: 6rem;
  }
  .button-64,
  .button-65,
  .button-66 {
    font-size: 24px;
    min-width: 196px;
  }
  .buttons {
    flex-direction: row;
    gap: 20px;
  }
}
</style>

<template>
  <div id="app">
    <Header></Header>
    <Projects></Projects>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/Header";
import Projects from "./components/Projects";
import Footer from "./components/Footer";

export default {
  name: "app",
  components: {
    Header,
    Projects,
    Footer
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Montserrat|Roboto&display=swap');
* {
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
    list-style-type: none;
  }

body {
    background: #FFF7F7;
    background: #d5e2bc;
    background: linear-gradient(49deg, #d5e2bc 68%, #d3c0d2 100%);
    color: #160F29;
    font-family: "Montserrat", sans-serif;
    display: flex;
    justify-content: center;
    padding: 5px;
  }  

h1 {
  background: -webkit-linear-gradient(#160F29, #368F8B);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-size: 1.5rem;
}
  
h2 {
  background: -webkit-linear-gradient(#368F8B, #160F29);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-size: 1rem;
}

@media (min-width: 992px) {
  h1 {
    font-size: 2rem;
  }

  h2 {
    font-size: 1.5rem;
  }

  body {
    min-height: 750px;
    height: 100vh
  }
}

</style>

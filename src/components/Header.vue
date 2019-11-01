<template>
  <div class="header">
    <div class="about-me">
      <h1>Gert Vandormael</h1>
      <h2>Junior web developer</h2>
    </div>
    <div class="social-media">
      <a href="https://github.com/gertvandormael"><i class="fab fa-github"></i></a>
      <a href="https://www.linkedin.com/in/gert-vandormael-56246a187/"><i class="fab fa-linkedin"></i></a>
    </div>
  </div>

</template>

<script>
export default {};
</script>

<style>

.header {
  display: flex;
  justify-content: space-between;
}

.fab {
  padding: 5px;
  font-size: 2rem;
  background: -webkit-linear-gradient(#160F29, #368F8B);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.fab:hover {
  background: -webkit-linear-gradient(#368F8B, #160F29);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) {
  .header {
    width: 800px;
  }

  .fab {
    font-size: 3rem;
  }
}

</style>
<template>
  <div id="app">
    <div id="wrapper">
      <nav class="navbar navbar-default">
        <div class="container">
          <a class="navbar-brand">
            Property Guru
          </a>
          <ul class="nav navbar-nav">
            <li>
              <a href="#">Hello</a>
            </li>
            <li>
              <a href="#">Goodbye</a>
            </li>
          </ul>
        </div>
      </nav>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

li {
  list-style: none;
}
#wrapper {
  position: absolute;
  z-index: 100;
  width: 100%;
}
</style>

<template>
  <div id="app">
    <h1>Hola Mundo</h1>
    <!--<Test msg="jeje Hola soy tu padre"/>-->
    <nav>
      <ul>
        <li>
          <router-link to="/test">
            Test
          </router-link>
        </li>
        <li>
          <router-link to="/">
            User
          </router-link>
        </li>
      </ul>
    </nav>
    <hr>
    <router-view></router-view>
  </div>
</template>

<script>
import Test from './components/Test'
import User from './components/User'

export default {
  name: 'App',
  components: {
    Test,
    User
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

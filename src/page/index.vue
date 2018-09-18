<template>
  <div id="app">
    <Header></Header>
    <div class="main">
      <ul>
        <li v-for="i in list" :key="i.id">
          <time v-text="i.createdAt"></time>
          <router-link :to="'/content/' + i.id">
            {{ i.title }}
          </router-link>
        </li>
      </ul>
      <div id="a"></div>
    </div>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from '@/components/header'
import Footer from '@/components/footer'
import $ from 'jquery'

export default {
  name: 'App',
  components: {Header, Footer},

  data () {
    return {
      list: []
    }
  },

  created () {
    this.getData()
  },

  methods: {
    getData () {
      let self = this
      $.get('http://localhost:8080/article/getArticleList', function (result) {
        self.list = result.data
      })
    }
  }
}
</script>

<style>
body {
  margin: 0px;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.main {
  margin: 20px 0px;
  height: auto;
}
</style>

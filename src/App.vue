<template>
  <div id="app">
    <Header />
    <router-view/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import 'reset-css'
import db from '@/firebase/init'


export default {
  components: {
    Header
  },
  created() {
    // db.collection('questions').get()
    // .then(snapshot => {
    //   snapshot.forEach(doc => {
    //     let question = doc.data()
    //     question.id = doc.id
    //     question.checked = false
    //     question.show = false
    //     this.$store.state.questions.push(question)
    //   })
    // })
    // db.collection('users').get()
    // .then(snapshot => {
    //   snapshot.forEach(doc => {
    //     let user = doc.data()
    //     user.id = doc.id
    //     user.role = 'user'
    //     this.$store.state.users.push(user)
    //   })
    // })
    this.$store.dispatch('getUsers')
  }
}
</script>


<style lang="scss">
@import '../node_modules/reset-css/sass/reset';

#app {
  position: relative;
  font-family: 'Lato', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>

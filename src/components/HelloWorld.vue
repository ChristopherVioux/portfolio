<template>
  <nav class="navbar">
    <router-link class="nav" to="/">Home</router-link> |
    <router-link class="nav" to="/about">About</router-link> |
    <router-link class="nav" to="/skills">Contact</router-link> |
  </nav>
  <template class="main">
    <div class="section intro">
      <div>{{ welcome }}</div>
      <div>{{ presentation }}</div>
      <div>{{ introduction }}</div>
    </div>
    <div style="background-color:#5ca3c7;" class="section">
      <div>
        {{ skills }}
      </div>
      <div class="skills">
        <div class="details">
          <v-text-field>{{ front }}</v-text-field>
          <div class="front" alt="front">
            <img class="icon" src='@/assets/Vue.png' alt="Vue">
            <img class="icon" src='@/assets/vuetify.png' alt="Vuetify">
            <img class="icon" src='@/assets/javascript.png' alt="Javascript">
          </div>
        </div>
        <div class="details">
          <v-text-field>{{ back }}</v-text-field>
          <div class="back" alt="back">
            <img class="icon" src='@/assets/mysql.png' alt="MySql">
            <img class="icon" src='@/assets/node.png' alt="NodeJs">
            <img class="icon" src='@/assets/sequelize.png' alt="Sequelize">
          </div>
        </div>
        <div class="details">
          <v-text-field>{{ tools }}</v-text-field>
          <div class="tools" alt="">
            <img class="icon" src='@/assets/github.png' alt="Github">
            <img class="icon" src='@/assets/git.png' alt="Git">
            <img class="icon" src='@/assets/vscode.png' alt="VSCode">
          </div>
        </div>
      </div>
    </div>
    <div class="section">Projets</div>
  </template>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      welcome: 'Hi ! I\'m',
      presentation: 'Christopher Vioux',
      introduction: 'I\'m a web developer, I love to code and I like to build websites.',
      skills: 'Skills',
      front: 'Front-End',
      back: 'Back-End',
      tools: 'Tools',
    };
  },
  name: 'HelloWorld',
  props: {
    msg: String,
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.hello {
  height: 100%;
  background: #b98942;
}
.navbar {
  background-color: #362B00;
}
.nav {
  color: #F6EEB4;
}
.main {
  color: #F6EEB4;
  height: 100%;
  background-color:#197CAE;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.section {
  height: 40%;
  display: flex;
  flex-direction: column;
}
.intro {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.skills {
  width: 100vw;
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.details {
  margin: 50px;
  height: 300px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.back {
  width: 75%;
  height: 70%;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
  align-content: space-around;
}
.front {
  width: 85%;
  height: 70%;
  margin-top:25px;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
}
.tools {
  width: 85%;
  height: 70%;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  margin-top:25px;
  justify-content: space-around;
}
.icon {
  height: 70px;
}
.vuetifyicon {
  height:60px;margin-top:5px;
}
</style>

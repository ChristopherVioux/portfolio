<template>
  <v-container style="display:flex; flex-direction:column">
    <nav class="navbar">
      <router-link class="nav" to="/skills">Contact</router-link>
    </nav>
    <template class="main">
    <div class="intro">
      <div style="font-size:5.5em;margin-left:-5px;">{{ welcome }}</div>
      <div style="font-size:2.5em;">{{ presentation }}</div>
      <div style="font-size:2em;margin-top:5px;">{{ introduction }}</div>
    </div>
    <div class="section">
      <div style="font-size: 1.5em;font-weight: bold;">
        {{ projects }}
      </div>
      <div class="projectList">
        <div class="project"></div>
        <div class="project"></div>
        <div class="project"></div>
      </div>
    </div>
    <div style="background-color:#4d3872;" class="section">
      <div style="font-size: 1.5em;font-weight: bold;">
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
    </template>
  </v-container>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      welcome: 'Hello and welcome !',
      presentation: 'I\'m Christopher',
      introduction: 'I\'m a web developer, I love to code and build websites !',
      skills: 'Skills',
      front: 'Front-End',
      back: 'Back-End',
      tools: 'Tools',
      projects: 'Here some projects I work on',
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
.navbar {
  background-color: #0A001B;
  display: flex;
  justify-content: flex-end;
}
.nav {
  color: #fffdec;
}
.main {
  color: #ededed;
  height: 95%;
  width: 100%;
  background-color:#0A001B;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.section {
  width:100%;
  display: flex;
  flex-direction: column;
}
.intro {
  width:100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin:250px 0 430px 150px;
  align-items: start;
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
  width:100%;
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
  height:60px;
  margin-top:5px;
}
.projectList {
  width: 100%;
  height: 500px;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
  margin-top:60px;
}
.project {
  width: 20%;
  height: 85%;
  background-color: #fffdec;
  border-radius: 5%;;
}
</style>

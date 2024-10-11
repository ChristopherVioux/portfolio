<!-- eslint-disable vuejs-accessibility/label-has-for -->
<template>
  <v-container class="container">
    <nav class="navbar">
      <router-link class="nav" to="/#/account">Home</router-link>
    </nav>
    <div class="contact-form">
      <div class="contact-title">Contact</div>
      <form @submit.prevent="handleSubmit" class="form">
        <div class="contactSection">
          <label for="name"></label>
          <input class="appForm" placeholder="Name" type="text" id="name" v-model="form.name" />
        </div>
        <div class="contactSection">
          <label for="phone"></label>
          <input class="appForm" placeholder="Phone" type="text" id="phone" v-model="form.phone" />
        </div>
        <div class="contactSection">
          <label for="email"></label>
          <input class="appForm" placeholder="Email" type="email" id="email" v-model="form.email" />
        </div>
        <div class="contactSection">
          <label for="message"></label>
          <textarea class="appForm" placeholder="Message" id="message" v-model="form.message" />
        </div>
        <button class="app-form-button" type="submit">SEND</button>
      </form>
    </div>
  </v-container>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue';

interface ContactForm {
  name: string
  email: string
  phone: string
  message: string
}

export default defineComponent({
  setup() {
    const form: ContactForm = reactive({
      name: '',
      email: '',
      phone: '',
      message: '',
    });

    const handleSubmit = async () => {
      try {
        // Envoi du formulaire ici
        console.log(form);
        // Exemple d'envoi de mail avec la bibliothèque emailjs
        // await sendMail(form)
      } catch (error) {
        console.debug(error);
      }
    };

    return { form, handleSubmit };
  },
});
</script>

<style scoped>
.nav {
  color: #fffdec;
  margin-right:25px;
}
.navbar {
  background-color: #0A001B;
  display: flex;
  justify-content: flex-end;
  width: 95%;
}
.contact-form {
  height: 70%;
  width: 45%;
  background: #1b083a;
  border-radius: 5px;;
  display: flex;
  flex-direction: row;
  align-items: center
}
.contactSection {
  display: flex;
  color: white;
  font-size: 1.3rem;
  flex-direction: column;
  width: 60%;
  align-content: center;
  justify-content: center;
  margin-top: 20px;
}
.container {
  display:flex;
  flex-direction:column;
  overflow-x:hidden;
  height: 100vh;
  width: 100%;
  align-items: center;
}
.contact-title {
  width:50%;
  font-size: 2.5em;
  font-weight: bold;
  margin-bottom:190px;
  color: #ea1d6f;
}
.form {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 50%;
}
.app-form-button {
  background: none;
  font-weight: bold;
  border: none;
  font-size: 1em;
  color: #ea1d6f;
  margin-top:15px;
  cursor: pointer;
  outline: none;
}
.appForm {
  width: 100%;
  padding: 10px 0;
  background: none;
  border: none;
  border-bottom: 1px solid #666;
  color: #ddd;
  font-size: 14px;
  text-transform: uppercase;
  outline: none;
  transition: border-color .2s;
}

.appForm::placeholder {
  color: #666;
}

.appForm:focus {
  border-bottom-color: #ddd;
}
.app-form-button:hover {
  color: #b9134f;
}
</style>

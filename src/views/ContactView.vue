<!-- eslint-disable vuejs-accessibility/label-has-for -->
<template>
  <v-container class="container">
    <nav class="navbar">
      <router-link class="nav" to="/#/account">Home</router-link>
    </nav>
    <div class="contact-form">
      <form @submit.prevent="handleSubmit" class="form">
        <div class="contactSection">
          <label for="name">Name :</label>
          <input type="text" id="name" v-model="form.name" />
        </div>
        <div class="contactSection">
          <label for="phone">Phone :</label>
          <input type="text" id="phone" v-model="form.phone" />
        </div>
        <div class="contactSection">
          <label for="email">Email :</label>
          <input type="email" id="email" v-model="form.email" />
        </div>
        <div class="contactSection">
          <label for="message">Message :</label>
          <textarea id="message" v-model="form.message" />
        </div>
        <button type="submit">Envoyer</button>
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

<style>
.nav {
  color: #fffdec;
}
.navbar {
  background-color: #0A001B;
  display: flex;
  justify-content: flex-end;
}
.contact-form {
  height: 100%;
}
.contactSection {
  display: flex;
  color: white;
  font-size: 1.3rem;
  flex-direction: column;
  width: 30%;
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
}
.form {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>

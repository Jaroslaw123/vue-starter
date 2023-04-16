<template>
  <div class="my-app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if = "loggedIn == false">Zaloguj się e-mailem 
      <input type="email" v-model="email">
      <button @click="wchodze()">Wchodzę</button>
    </div>
    <div v-else-if = "loggedIn == true">Witaj {{ email }}
    <button @click="wyloguj()">Wchodzę</button>
  </div>
  </div>
</template>

<script>
  import "milligram";
export default {

  data() {
  return {
    email: 'j@agh.edu.pl',
    password: '',
    loggedIn: false
  };
},
methods: {
      wchodze() {
        this.loggedIn = true;
      },
      wyloguj() {
        this.loggedIn = false;
      }
  },

}
</script>
<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>
<!--     
    <div v-if="!email.includes('@')">Twój adres email jest niepoprawny</div>
    <div v-else-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi, ponieważ ma {{email.length }} znaków</div> -->
<template>
  <div>
    <h1>Witaj w systemie zpisów na zajęcia</h1>
    <div v-if="isUserLoggedIn"> 
    <h2>Witaj {{ email }} </h2> 
    <a @click="onClickLogOut()">Wyloguj</a>
    </div>
    <div v-else>
      Zaloguj się e-mailem<input type="email" v-model="email">
    <button @click='onClickLogIn()'>Wchodzę</button>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      email: '',
      isUserLoggedIn: false,
      password: ''
    };
  },
  methods: {
    onClickLogIn() {
      if (this.email.length == 0) {
        alert("E-mail nie może być pusty");
      } else {
        this.isUserLoggedIn = true;
      }
    },
    onClickLogOut() {
      this.isUserLoggedIn = !this.isUserLoggedIn;
      this.email = '';
    }
  }
}
</script>

<style>

</style>

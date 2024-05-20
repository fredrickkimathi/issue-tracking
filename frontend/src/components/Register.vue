<template>
  <div class="register-page">
    <div class="google">
      <div class="google-button" @click="socialLogin">
        <img class="google-icon" href="#" src="@/assets/googleicon.png"    alt="Image alt"/>
        <a class="google-word">Continue with Google</a>
      </div>
    </div>
    <p>OR</p>
    <form @submit.prevent="register" class="register-child">
      <input type="email" placeholder="Email address..." v-model="email" />
      <input type="password" placeholder="password..." v-model="password" />
      <button type="submit">Register</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      email: '',
      password: '',
    };
  },
  methods: {
    socialLogin() {
      // Handle social login
    },
    register() {
      axios.post('/api/register', {
        email: this.email,
        password: this.password,
      })
      .then(response => {
        // Handle successful registration
      })
      .catch(error => {
        // Handle error
      });
    },
  },
};
</script>
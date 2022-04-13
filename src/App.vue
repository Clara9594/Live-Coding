<template>
  <div id="app">
    <div v-if="isLogin == false">
        <input v-model = "email" placeholder="Masukkan Email Anda"/>
        <br>
        <input v-model = "password" type="password" placeholder="Masukkan Password Anda"/>
        <button v-on:click="login()">Login</button>
    </div>
    <div v-else>
        <p>Selamat Siang</p>
        <span>{{currentTime}}</span>
        <span>{{email}}</span>
        <br>
        <button v-on:click="logout()">Logout</button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      email : '',
      password : '',
      isLogin : false,
      currentTime : new Date(),
    }
  },
  methods:{
    login(){
        this.isLogin = true;
        this.email = '';
        this.password = '';
    },
    logout(){
        this.isLogin = false;
    }
  }
}
</script>


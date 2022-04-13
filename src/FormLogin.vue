<template>
  <div id="app">
    <div v-if="isLogin == false">
      <p>Halaman Login</p>
      <input v-model = "email" placeholder="Masukkan Email Anda"/>
      <br>
      <input v-model = "password" type="password" placeholder="Masukkan Password Anda"/>
      <br>
      <button v-on:click="login()">Login</button>
    </div>
    <div v-else>
      <p>Selamat Siang, {{splitEmail}}</p>
      <span>Hari ini : {{currentTime}}</span>
      <br>
      <span>Email Login : {{email}}</span>
      <br>
      <button v-on:click="logout()">Logout</button>
    </div>
  </div>
</template>

<script>

export default {
  data(){
    return{
      email : '',
      password : '',
      isLogin : false,
      splitEmail : null,
      currentTime : new Date(),
    }
  },
  methods:{
    login(){
      if(this.email.length < 10 || this.email.length > 15){
        alert('Failed')
      }else{
        alert('Success')
        this.isLogin = true;
        localStorage.setItem('email', this.email);
        this.splitString();
      }
    },
    logout(){
      this.isLogin = false;
      this.email = '';
      this.password = '';
    },
    splitString(){
      this.splitEmail = this.email.split('@')[0];
    }
  }
}
</script>


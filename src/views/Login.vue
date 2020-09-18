<template>
  
    <div class="container d-flex justify-content-center mt-5">
        <div>
        <h1>Login Page</h1>
        <div class="alert alert-danger"  v-if="mess != ''" role="alert">
            {{mess}}
          </div>
        <form @Submit.prevent="login">
          <div class="form-group">
            <label for="exampleInputEmail1">User name</label>
            <input type="text" v-model="username" class="form-control" required id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Username">
          </div>
          <div class="form-group">
            <label for="exampleInputPassword1">Password</label>
            <input type="password" v-model="password" class="form-control" required id="exampleInputPassword1" placeholder="Password">
          </div>
          <div class="d-flex justify-content-between">  

            <router-link to="/register">Register</router-link>
            <button class="btn btn-primary">Login</button>
          </div>
        </form>
        </div>
    </div>
   
  
</template>

<script>

export default {
  
  name: 'Login',

  data () {
      return {
        username: "",
        password: "",
        mess: "",
      }
  },

  methods: {
    login () {
      this.mess = "";
        var username = localStorage.getItem('username');
        var password = localStorage.getItem('password');
        if(username === null || password === null) {
            this.mess="You need to register first";
            return
        }

        if(username != this.username || password != this.password) {
          this.mess="Invalid username or password";
          return
        }

        sessionStorage.setItem('auth', true);
        this.$router.push('/home');
      
    },
  },
  
}
</script>

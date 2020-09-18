<template>
    <div class="container d-flex justify-content-center mt-5">
        
        <div>
          <h1>Register Page</h1>
          <div class="alert alert-success" v-if="mess" role="alert">
            Successfull registered!
          </div>
          <form @Submit.prevent="submit">
            <div class="form-group">
              <label for="exampleInputEmail1">User name</label>
              <input type="text" v-model="username" class="form-control" required  placeholder="Username">
            </div>
            <div class="form-group">
              <label for="exampleInputPassword1">Password</label>
              <input type="password" v-model="password" class="form-control" required  placeholder="Password">
            </div>
            <div class="d-flex justify-content-between">  

              <router-link to="/">Login</router-link>
              <button class="btn btn-primary">Register</button>
            </div>
          </form>
        </div>
    </div>
   
</template>



<script>

export default {
  name: 'Register',
  
  data () {
      return {
        username: "",
        password: "",
        mess: false,
      }
  },
  methods: {
    submit () {

        localStorage.setItem('username', this.username);
        localStorage.setItem('password', this.password);
        this.mess = true;
        
    },
  }
}
</script>



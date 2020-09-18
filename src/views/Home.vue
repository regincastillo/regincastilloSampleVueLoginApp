<template>
  <div class="container mt-5 text-center">
    <h1>Home Page</h1>
    <img alt="Vue logo" src="../assets/logo.png">
    <div class="mt-5 d-flex justify-content-around" >
    <button type="button" class="btn  btn-danger" @click="removeAccount">Remove account</button>  
    <button type="button" class="btn  btn-secondary" @click="logout">Logout</button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',

  beforeUnmount (){
     sessionStorage.clear();
  },
  methods: {
    logout () {
      this.$router.push('/');
    },
    removeAccount () {
      localStorage.clear();
      this.logout();
    }
  }
}
</script>

<template>
  
      <div class="col-md-12">
        <form @submit.prevent="onSubmit">
          <h2>Registrati</h2>
          <hr>
          <div class="form-group">
            <label for="name">Nome</label>
            <input class="form-control" type="name" id="name" v-model="name">
          </div>
          <div class="form-group">
            <label for="surname">Cognome</label>
            <input class="form-control" type="surname" id="surname" v-model="surname">
          </div>
          <div class="form-group">
            <label for="email">Mail</label>
            <input class="form-control" type="email" id="email" v-model="email">
          </div>
          <div class="form-group">
            <label for="password">Password</label>
            <input class="form-control" type="password" id="password" v-model="password">
          </div>
          <button type="submit" class="btn btn-dark">Salva</button>
    </form>
  
    
  </div>
</template>

<script>

import axios from 'axios';

export default {
  state: {
    idToken : 'casa xxxxxx',
    idUser : null,
    user : null
  },
  data () {
    return {
      name : '',
      surname : '',
      email : '',
      password : ''
    }
  },
  methods : {
    onSubmit(){
      const formData = {
        name : this.name,
        surname : this.surname,
        email : this.email,
        password : this.password
      }
      console.log(formData);
      
      axios.post('https://identitytoolkit.googleapis.com/v1/accounts:signUp?key=AIzaSyB9XbjuK9_PDRjyUFO3XyqcX5Qbdra845w',
      {   
        email : formData.email,
        password : formData.password,
        returnSecureToken : true
      })
      .then(res => console.log(res))
      .catch(error => console.log(error));
     
    },
}
  }

</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
form {
  text-align: center;
        width: 90%;
        margin-left:auto;
        margin-right:auto;
        padding:50px;
        margin-bottom: 30px;
        background: -moz-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
        background: -webkit-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
        background: linear-gradient(135deg, #ff7e00 0%, #a016f7 100%);
        filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff7e00', endColorstr='#a016f7', GradientType=1);
        border-radius:5px;
        position:relative;
        font-family: 'Libre Franklin', sans-serif;
    }

</style>
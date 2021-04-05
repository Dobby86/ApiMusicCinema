<template>
  <div class="container">
    <form @submit.prevent="onSubmit">
      <h2>Login</h2>
      <hr>
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
  data () {
    return {
      email : 'dobermann866@live.it',
      password : 'qwerty'
    }
  },
  methods : {
    onSubmit(){
      const formData = {
        
        email : this.email,
        password : this.password
      }
      console.log(formData);
      axios.post('https://identitytoolkit.googleapis.com/v1/accounts:signInWithPassword?key=AIzaSyB9XbjuK9_PDRjyUFO3XyqcX5Qbdra845w',
      {
      
        email : formData.email,
        password : formData.password,
        returnSecureToken : true
      })
      .then(res => console.log(res)
      )
      .catch(error => console.log(error));
    }
  },
  state:{

  },
  mutations:{

  },
  actions:{
       
  },
  getters:{

  }
      
}
</script>

<style scoped>
   
    
    form{
        width: 90%;
        margin-left:auto;
        margin-right:auto;
        padding:50px;
        background: -moz-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
        background: -webkit-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
        background: linear-gradient(135deg, #ff7e00 0%, #a016f7 100%);
        filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff7e00', endColorstr='#a016f7', GradientType=1);
            border-radius:5px;
            position:relative;
            font-family: 'Libre Franklin', sans-serif;
    }

    
</style>
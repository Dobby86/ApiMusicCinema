<template>

<div class="row">
    


    <div class="col-md-12">
        
        <div class="card">
            <div class="card-header"> <h3> Mostra gli Album</h3></div>
                    <div class="card-body">
                            <div class="list-group">
                                <div v-if="loading" class="alert alert-dark" role="alert">
                                    Loading......
                                </div>
                                <!-- ///// -->

                                <ul v-for="p in music" v-bind:key="p">    
                                    <img :src="p.poster" alt="Movie Poster" class="featured-img"/>
                                    <br>
                                    <br>
                                    <li scope="row"><h2>{{p.author}}</h2></li>
                                    <li><h2> {{p.title}} </h2></li>
                                    <li><h2> {{p.year}}</h2></li>   
                                       
                                </ul>
                            
                                <!-- <a href="#" class="btn btn-primary" @click="invia()">Salva</a> -->
                                <button @click="invia()" type="button" class="btn btn-primary">Mostra</button>
                                
                            </div>

                    </div>
            </div>
    </div>

 </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'

export default {
 
  
  data(){
      return{
          music: [],
          post:{
              id:'35',
              title: '',
              body:''
          },
          loading: false,
          success:false
      }
      
  },
  props: {
   title: String,
   description: String
  },
      methods: {
 
         invia(){
            var url = 'https://flynn.boolean.careers/exercises/api/array/music';
         
            this.loading= true;

            axios.get(url)
            .then(res => {
                this.music= res.data.response;
                this.loading= false;
                console.log(res.data.response)
            } )
            .catch(err => {
                this.loading= false;
                console.log(err)
            } );
        }  
       
     
  }
  
}
</script>

<style scoped>
*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

.card{
    margin-bottom: 50px;
    margin-top: 90px;
}
.card-body{
    min-width: 400px;
    min-height: 450px;
    background: -moz-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
    background: -webkit-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
    background: linear-gradient(135deg, #ff7e00 0%, #a016f7 100%);
    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff7e00', endColorstr='#a016f7', GradientType=1);
    display: flex;
    justify-content: center;
    align-items: center;
    
}
.card-header{
    min-width: 400px;
    height: 50px;
     background: -moz-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
    background: -webkit-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
    background: linear-gradient(135deg, #ff7e00 0%, #a016f7 100%);
    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff7e00', endColorstr='#a016f7', GradientType=1);
    text-align: center;
}
img{
    height: 200px;
    width: 200px;
    -webkit-box-shadow: 10px 10px 5px 0px rgba(217,193,217,1);
    -moz-box-shadow: 10px 10px 5px 0px rgba(217,193,217,1);
     box-shadow: 10px 10px 5px 0px rgba(217,193,217,1);
}
li {
    list-style: none;
    font-size: 26px;
    color: black;
}
ul {
    list-style-type:none;
    font-size: 26px;
    margin-top: 20px;
    
}

/* header..footer */
#flipkart-navbar {
    background-color: #2874f0;
    color: #FFFFFF;
}

.row1{
    padding-top: 10px;
    padding-right: 50px;
}

.row2 {
    padding-bottom: 20px;
}

.flipkart-navbar-input {
    padding: 11px 16px;
    border-radius: 2px 0 0 2px;
    border: 0 none;
    outline: 0 none;
    font-size: 15px;
}

.flipkart-navbar-button {
    background-color: #ffe11b;
    border: 1px solid #ffe11b;
    border-radius: 0 2px 2px 0;
    color: #565656;
    padding: 10px 0;
    height: 43px;
    cursor: pointer;
}

.cart-button {
    background-color: #2469d9;
    box-shadow: 0 2px 4px 0 rgba(0, 0, 0, .23), inset 1px 1px 0 0 hsla(0, 0%, 100%, .2);
    padding: 10px 0;
    text-align: center;
    height: 41px;
    border-radius: 2px;
    font-weight: 500;
    width: 120px;
    display: inline-block;
    color: #FFFFFF;
    text-decoration: none;
    color: inherit;
    border: none;
    outline: none;
}

.cart-button:hover{
    text-decoration: none;
    color: #fff;
    cursor: pointer;
}

.cart-svg {
    display: inline-block;
    width: 16px;
    height: 16px;
    vertical-align: middle;
    margin-right: 8px;
}

.item-number {
    border-radius: 3px;
    background-color: rgba(0, 0, 0, .1);
    height: 20px;
    padding: 3px 6px;
    font-weight: 500;
    display: inline-block;
    color: #fff;
    line-height: 12px;
    margin-left: 10px;
}

.upper-links {
    display: inline-block;
    padding: 0 11px;
    line-height: 23px;
    font-family: 'Roboto', sans-serif;
    letter-spacing: 0;
    color: inherit;
    border: none;
    outline: none;
    font-size: 12px;
}

.dropdown {
    position: relative;
    display: inline-block;
    margin-bottom: 0px;
}

.dropdown:hover {
    background-color: #fff;
}

.dropdown:hover .links {
    color: #000;
}

.dropdown:hover .dropdown-menu {
    display: block;
}

.dropdown .dropdown-menu {
    position: absolute;
    top: 100%;
    display: none;
    background-color: #fff;
    color: #333;
    left: 0px;
    border: 0;
    border-radius: 0;
    box-shadow: 0 4px 8px -3px #555454;
    margin: 0;
    padding: 0px;
}

.links {
    color: #fff;
    text-decoration: none;
}

.links:hover {
    color: #fff;
    text-decoration: none;
}

.profile-links {
    font-size: 12px;
    font-family: 'Roboto', sans-serif;
    border-bottom: 1px solid #e9e9e9;
    box-sizing: border-box;
    display: block;
    padding: 0 11px;
    line-height: 23px;
}

.profile-li{
    padding-top: 2px;
}

.largenav {
    display: none;
}

.smallnav{
    display: block;
}

.smallsearch{
    margin-left: 15px;
    margin-top: 15px;
}

.menu{
    cursor: pointer;
}

@media screen and (min-width: 768px) {
    .largenav {
        display: block;
    }
    .smallnav{
        display: none;
    }
    .smallsearch{
        margin: 0px;
    }
}

/*Sidenav*/
.sidenav {
    height: 100%;
    width: 0;
    position: fixed;
    z-index: 1;
    top: 0;
    left: 0;
    background-color: #fff;
    overflow-x: hidden;
    transition: 0.5s;
    box-shadow: 0 4px 8px -3px #555454;
    padding-top: 0px;
}

.sidenav a {
    padding: 8px 8px 8px 32px;
    text-decoration: none;
    font-size: 25px;
    color: #818181;
    display: block;
    transition: 0.3s
}

.sidenav .closebtn {
    position: absolute;
    top: 0;
    right: 25px;
    font-size: 36px;
    margin-left: 50px;
    color: #fff;        
}

@media screen and (max-height: 450px) {
  .sidenav a {font-size: 18px;}
}

.sidenav-heading{
    font-size: 36px;
    color: #fff;
}
/* carousel */
/*search box css start here*/
.search-sec{
    padding: 2rem;
}
.search-slt{
    display: block;
    width: 100%;
    font-size: 0.875rem;
    line-height: 1.5;
    color: #55595c;
    background-color: #fff;
    background-image: none;
    border: 1px solid #ccc;
    height: calc(3rem + 2px) !important;
    border-radius:0;
}
.wrn-btn{
    width: 100%;
    font-size: 16px;
    font-weight: 400;
    text-transform: capitalize;
    height: calc(3rem + 2px) !important;
    border-radius:0;
}
@media (min-width: 992px){
    .search-sec{
        position: relative;
        top: -114px;
        background: rgba(26, 70, 104, 0.51);
    }
}

@media (max-width: 992px){
    .search-sec{
        background: #1A4668;
    }
}

</style>
<template>
  <div class="testCont col-md-12">
     
   <h3 class="pb-3 mb-4 font-italic border-bottom">
     {{ Title }}
   </h3>
  
   <div class="row">
      <div class="col-md-4">
         <div class="card mb-4 text-white bg-dark">
            
            <img class="card-img-top" :src="Poster" />
            <div class="card-body">
               <!-- <h5 class="card-title">{{ imdbID }}</h5> -->
               <p class="card-text">{{ Year }}</p>
               <p class="card-text">{{ Type }}</p>
               
               
            </div>
         </div>
      </div>
      <div class="col-md-4">
         <div class="card mb-4 text-white bg-dark">
            <img class="card-img-top" :src=" Poster " />
            <div class="card-body">
               <!-- <h5 class="card-title">{{ imdbID }}</h5> -->
               <p class="card-text">{{ Year }}</p>
               <p class="card-text">{{ Type }}</p>
              
            </div>
         </div>
      </div>
      <div class="col-md-4">
         <div class="card mb-4 text-white bg-dark">
           <img class="card-img-top" :src=" Poster " />
            <div class="card-body">
              
               <p class="card-text">{{ Year }}</p>
               <p class="card-text">{{ Type }}</p>
              
            </div>
         </div>
      </div>
      <!--  -->
   </div>
  
   <!-- fine -->
</div>
</template>

<script>
export default {
   props:{
      Title:{
          type: String,
      default: " ",
   },
   Poster:{
          type: String,
      default: " ",
   },
   
   Type:{
          type: String,
      default: " ",
   },
   imdbID:{
          type: String,
      default: " ",
   },
   Year:{
      type: String,
      default: " ",
   }
      }
     

}
</script>

<style scoped>

h3 {
   text-align: center;
}
button{
   text-align: center;
}
.card-img-top {
   max-width: 100%;
    height: 350px;
    padding:25px;
}
.card-text{
   text-align: center;
   font-size: 21px;
   font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
}
.social-card-header {
    position: relative;
    display: -ms-flexbox;
    display: flex;
    -ms-flex-align: center;
    align-items: center;
    -ms-flex-pack: center;
    justify-content: center;
    height: 96px;
}
.social-card-header i {
    font-size: 32px;
    color:#FFF;
}
.bg-facebook {
    background-color:#3b5998;
}
.text-facebook {
    color:#3b5998;
}
.bg-google-plus{
    background-color:#dd4b39;
}
.text-google-plus {
    color:#dd4b39;
}
.bg-twitter {
    background-color:#1da1f2;
}
.text-twitter {
    color:#1da1f2;
}
.bg-pinterest {
    background-color:#bd081c;
}
.text-pinterest {
    color:#bd081c;
}
.share:hover {
        text-decoration: none;
    opacity: 0.8;
}

</style>
<template>

   <div class="col-lg-12">
       <button @click="invia()" type="button" class="col-lg-4 offset-lg-4 btn btn-primary">Show Movies</button>
       <hr>
     <Card v-for="post in posts" v-bind:key="post"
      :Poster="post.Poster"
      :Title="post.Title"
      :imdbID="post.imdbID" 
      :Type="post.Type"
      :Year="post.Year"

      />
   </div>
   
</template>

<script>
import axios from 'axios';
export default {
   data(){
      return{
         posts: [
            {Poster: " ", Title: " ",imdbID: " ", Type: " ", Year: " "},
             {Poster: " ", Title: " ",imdbID: " ", Type: " ", Year: " "},
              {Poster: " ", Title: " ",imdbID: " ", Type: " ", Year: " "},
               {Poster: " ", Title: " ",imdbID: " ", Type: " ", Year: " "},
                {Poster: " ", Title: " ",imdbID: " ", Type: " ", Year: " "},
 
          
         ]
      }
   },
         methods: {
 
         invia(){

            var url = 'http://www.omdbapi.com/?apikey=872879a5&s=batman';      
            // this.loading= true;

            axios.get(url)
            .then(res => {
                this.posts= res.data.Search;
               //  this.loading= false;
                console.log(res.data.Search)
            } )
            .catch(err => {
               //  this.loading= false;
                console.log(err)
            } );
        }    
  }
  
}
</script>

<style>

</style>
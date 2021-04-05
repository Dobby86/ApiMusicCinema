<template>

  <div class="container">
    <div>
       
      <h1 class="title">
        ApiMusic
      </h1>
      <div class="links">

        <NuxtLink to="/apiGen">Api |</NuxtLink>

        <NuxtLink to ="/plusless">PlusLess |</NuxtLink>

         <NuxtLink to ="/test">Test |</NuxtLink>
        
      </div>
    </div>
  </div>
</template>

<script>
export default {
  

}
</script>

<style>
/* header */
.container {
 
  min-height: 50vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
a{
    text-decoration: none;
    color: #35495e;
}
a:hover{
    color: green;
}
.title {
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
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}


.links {
  padding-top: 15px;
}
</style>

<template>
        
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
            <a class="navbar-brand" href="#">ApiMusic</a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon" @click="openNav"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNavDropdown">
                <ul class="navbar-nav">

                    <li class="nav-item">
                        <NuxtLink to ="/">Home</NuxtLink>
                    </li>
                    <li class="nav-item active">
                        <NuxtLink to="/music">Music</NuxtLink>
                    </li>
                    <li class="nav-item">
                        <NuxtLink to ="/plusless">PlusLess</NuxtLink>
                    </li>
                    <li class="nav-item">
                        <NuxtLink to ="/cinema">Cinema</NuxtLink>
                    </li>
                    <li class="nav-item">
                        <NuxtLink to ="/login">Login</NuxtLink>
                    </li>
                    <li class="nav-item">
                        <NuxtLink to ="/register">Register</NuxtLink>
                    </li>
                          
                </ul>
            </div>
            <!-- hamb -->
            <div id="mySidenav" class="sidenav">
                    <div class="container">
                        <span class="sidenav-heading">Menu</span><a href="javascript:void(0)" class="closebtn" @click="closeNav">X</a>

                          <NuxtLink class="dropdown-item" to="/" tag="li" active-class="active" exact>Home</NuxtLink>

                        <NuxtLink class="dropdown-item" to="/apiGen" tag="li" active-class="active" exact>Api</NuxtLink>

                        <NuxtLink class="dropdown-item" to="/plusless" tag="li" active-class="active" exact>PlusLess</NuxtLink> 
                        <NuxtLink class="dropdown-item" to="/test" tag="li" active-class="active" exact>Test</NuxtLink> 
                       
                    </div>
                    
                                          
                                             
            </div>
</nav>
</template>

<script>
export default {
    methods:{
        openNav() {
            document.getElementById("mySidenav").style.display = "block";
            // document.getElementById("flipkart-navbar").style.width = "50%";
            document.body.style.backgroundColor = "rgba(0,0,0,0.4)";
        },

        closeNav() {
            // document.getElementById("mySidenav").style.width = "0";
            document.getElementById("mySidenav").style.display = "none";
            document.body.style.backgroundColor = "rgba(0,0,0,0)";
        },
    }
}
</script>

<style scoped>

#mySidenav{
    
    background: -moz-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
    background: -webkit-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
    background: linear-gradient(135deg, #ff7e00 0%, #a016f7 100%);
    width: 100vw;
    min-height: 100vh;
    display: none;

}
nav{
    background: -moz-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
    background: -webkit-linear-gradient(-45deg, #ff7e00 0%, #a016f7 100%);
    background: linear-gradient(135deg, #ff7e00 0%, #a016f7 100%);
    margin-bottom: 50px;
}
li{
    margin: 10px;
    padding-right: 10px;

}
a{
    text-decoration: none;
    color: #35495e;
}
a:hover{
    color: green;
}
</style>
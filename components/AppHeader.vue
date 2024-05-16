<template>
    <header>
        <nav class="navbar navbar-expand-lg navbar-dark">
            <div class="container d-flex justify-content-center align-items-center">
                <nuxt-link to="/" class="navbar-brand d-flex text-black">
                    <img src="/public/sunflower-terraria.gif" alt="" class="logo p-2">
                    <h2 class="logo-name mt-2">Nannat</h2>
                </nuxt-link>
                <!-- <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button> -->
                <!-- <div class="collapse navbar-collapse" id="navbarNav">
                    <ul class="navbar-nav ml-auto">
                        <li class="nav-item">   
                            <nuxt-link to="/home" class="nav-link ">Home</nuxt-link>
                        </li>
                        <li class="nav-item">
                            <nuxt-link to="/product" class="nav-link ">Product</nuxt-link>
                        </li>
                        <li class="nav-item">
                            <nuxt-link to="/about" class="nav-link ">About</nuxt-link>
                        </li>
                        <li class="nav-item">
                            <nuxt-link to="/contact" class="nav-link ">Contact</nuxt-link>
                        </li>
                    </ul>
                    
                </div> -->
            </div>
        </nav>
    </header>
</template>

<script setup></script>


<style scoped>
/* Add hover effect to navbar links */
.nav-link{
    color:#4e3900;
    text-decoration: none,
}

.nav-link:hover {
    color: rgb(164, 182, 0);
    /* background-color: #967f00;  */
}
.logo{
    width:45px;
    height:45px;

}
.logo-name{
    font-style:oblique;
    color:#fff;
}
.logo-name:hover{
    color: #fff;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

header{
     background-color: #E1AFD1;
 }
 


</style>


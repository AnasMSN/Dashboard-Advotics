<template>
    <div>
    <b-navbar toggleable="lg" type="light" variant="white" class="border-bottom" fixed="top">
        <b-navbar-brand><img alt="Advotics logo" height="50px" src="@/assets/advotics_logo.jpg"></b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">

            <b-nav-item class="h-100 mr-4" style="width:200px" right>
                <div class="row h-100">
                    <div class="col-8 float-right">
                        <div class="float-right" style="font-size:14px">Username</div>
                        <div class="float-right" style="font-size:10px">Company Name</div>
                    </div>
                    <div class="col">
                        <img class="align-self-center" alt="profile" height="30px" src="@/assets/profile.svg">
                    </div>
                    
                    
                </div>
            </b-nav-item>

            <b-nav-item class="h-100" right ><img class="align-self-center" alt="logout" height="25px" src="@/assets/logout@2x.png"></b-nav-item>

        </b-navbar-nav>
        </b-collapse>
    </b-navbar>
    </div>
  
</template>

<style>

nav {
    box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.1), 0 3px 10px 0 rgba(0, 0, 0, 0.19);
}
    
</style>

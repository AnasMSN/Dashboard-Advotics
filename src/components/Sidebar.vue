<template>
    <div>
         <!-- Side navigation -->
        <div class="sidenav">
            <a href="#">A</a>
            <a href="#">S</a>
        </div>
    </div>
  
</template>

<style scoped>


/* The sidebar menu */
.sidenav {
  height: 100%; /* Full-height: remove this if you want "auto" height */
  width: 80px; /* Set the width of the sidebar */
  position: fixed; /* Fixed Sidebar (stay in place on scroll) */
  background-color: white; /* Black */
  overflow-x: hidden; /* Disable horizontal scroll */
  padding-top: 90px;
  border-right-style: solid;
  border-color:darkgrey;
  border-width: 1px;
  align-content: center;
  justify-content: center;

}

/* The navigation menu links */
.sidenav a {
  padding: 6px 8px 6px 16px;
  text-decoration: none;
  font-size: 25px;
  color: #818181;
  display: block;
}

/* When you mouse over the navigation links, change their color */
.sidenav a:hover {
  color: #f1f1f1;
}


</style>
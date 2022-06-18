<template>
  <div class="container">
    <nav>Navbar</nav>
    <main id="main">Main</main>
     <div id="sidebar"> SideBar</div>
     <div id="content1">Content 1</div>
     <div id="content2">Content 2</div>
     <div id="content3"> Content 3</div>
    <footer id="btm">bottom</footer>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style >

:root{
  --main-radius:6px;
  --main-padding:6px;
}
.container{
  display: grid;
  height:100vh;
  width:100vh;
  grid-template-columns: 6fr 6fr 6fr 6fr;
  grid-template-rows: 0.2fr 1.5fr 1.2fr 0.8fr;
  grid-template-areas: 
  "nav nav nav nav"
  "sidebar main main main"
  "sidebar content1 content2 content3"
  "sidebar btm btm btm";
  grid-gap: 0.3rem;
  font-family: 'Courier New', Courier, monospace;
  font-weight: 600;
  text-transform: uppercase;
  color: black;
  align-content: center;
  text-align: center;

 
}
nav{
  background-color: aqua;
  grid-area: nav;
  border-radius: var(--main-radius);
  padding-top: var(--main-padding);
}
#main{
  background-color: brown;
  grid-area: main;
  border-radius: var(--main-radius);
  padding-top: var(--main-padding);
}
#sidebar{
  background-color: beige;
  grid-area: sidebar;
  border-radius: var(--main-radius);
  padding-top: var(--main-padding);
}
#content1{
  background-color: blueviolet;
  grid-area: content1;
  border-radius: var(--main-radius);
  padding-top: var(--main-padding);
}
#content2{
  background-color: aquamarine;
  grid-area: content2;
  border-radius: var(--main-radius);
  padding-top: var(--main-padding);
}
#content3{
  background-color: blue;
  grid-area: content3;
  border-radius: var(--main-radius);
  padding-top: var(--main-padding);
}
#btm{
  background-color: rgb(17, 73, 54) ;
  grid-area: btm;
  border-radius: var(--main-radius);
  padding-top: var(--main-padding);
}
@media only screen and (max-width:550px){
  .container{
    grid-template-columns: 1fr;
    grid-template-rows: 0.4fr 0.4fr 2.2fr 1.2fr 1.2fr 1fr ;
    grid-template-areas: 
    "nav"
    "sidebar"
    "main"
    "content1"
    "content2"
    "content3"
    "btm";
  }
}
</style>

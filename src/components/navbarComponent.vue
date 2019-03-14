<template>
  <div class="hello">

    <v-toolbar dark v-bind:class="active" v-on:click.prevent>
    <v-toolbar-side-icon></v-toolbar-side-icon>
    <v-toolbar-title>Title</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
      <v-btn flat class="home" v-on:click="makeActive('home')">Home</v-btn>
      <v-btn flat class="projects" v-on:click="makeActive('projects')">Projects</v-btn>
      <v-btn flat class="services" v-on:click="makeActive('services')">Services</v-btn>
      <v-btn flat class="contact" v-on:click="makeActive('contact')" >Contant</v-btn>
    </v-toolbar-items>
  </v-toolbar>
  <v-alert
      :value="true"
      type="success"
    >
    <p>You chose <b>{{ active }}</b></p>
    </v-alert>
    </div>
</template>

<script>
export default {
  name: 'navbar',
  data() {
    return{
      active: 'home'
      
    }
  },
  methods :{
    makeActive: function(item)
    {  this.active = item;
        }
    }
  }
  
</script>

<style scoped>
/* *{
    margin:0;
    padding:0;
}

body{
    font:15px/1.3 'Open Sans', sans-serif;
    color: #5e5b64;
    text-align:center;
}

a, a:visited {
    outline:none;
    color:#389dc1;
}

a:hover{
    text-decoration:none;
}

section, footer, header, aside, nav{
    display: block;
}


nav{
    display:inline-block;
    margin:60px auto 45px;
    background-color:#5597b4;
    box-shadow:0 1px 1px #ccc;
    border-radius:2px;
}

nav a{
    display:inline-block;
    padding: 18px 30px;
    color:#fff !important;
    font-weight:bold;
    font-size:16px;
    text-decoration:none !important;
    line-height:1;
    text-transform: uppercase;
    background-color:transparent;

    -webkit-transition:background-color 0.25s;
    -moz-transition:background-color 0.25s;
    transition:background-color 0.25s;
}

nav a:first-child{
    border-radius:2px 0 0 2px;
}

nav a:last-child{
    border-radius:0 2px 2px 0;
}

nav.home .home,
nav.projects .projects,
nav.services .services,
nav.contact .contact{
    background-color:#e35885;
}

p{
    font-size:22px;
    font-weight:bold;
    color:#7d9098;
}

p b{
    color:#ffffff;
    display:inline-block;
    padding:5px 10px;
    background-color:#c4d7e0;
    border-radius:2px;
    text-transform:uppercase;
    font-size:18px;
} */

</style>

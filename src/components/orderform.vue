<template>
  <v-flex xs12 grid-list-md text-xs-center>
    <v-card>
      <v-card-text class="px-0">
        <form id="main" v-cloak>
          <h1>Services</h1>
          <ul>
            <li
              
              v-for="(service,index) in services" :key="index"
              v-on:click="toggleActive(service)"
              v-bind:class="{ 'active': service.active}"
            >
              {{service.name}}
              <span>{{service.price}}$</span>
            </li>
          </ul>

          <div class="total">
            Total:
            <span>{{total()}}$</span>
          </div>
          <v-btn btn v-if="show">
            <v-icon size="25">add_shopping_cart</v-icon>Add To Cart
          </v-btn>
        </form>
      </v-card-text>
    </v-card>
  </v-flex>
</template>
<script>
export default {
  name: "orderform",
  data() {
    return {
        show:true
        ,
      services: [
        {
          name: "Web Development",
          price: 300,
          active: true
        },
        {
          name: "Design",
          price: 400,
          active: false
        },
        {
          name: "Integration",
          price: 250,
          active: false
        },
        {
          name: "Training",
          price: 220,
          active: false
        }
      ]
    };
  },
  methods: {
    toggleActive: function(s) {
      s.active = !s.active;
    },
    total: function() {
      var total = 0;

      this.services.forEach(function(s) {
        if (s.active) {
          total += s.price;
        }
      });

     

      return total;
    
    }
  }
};
</script>

<style scoped>
@import url(https://fonts.googleapis.com/css?family=Cookie);

/* Hide un-compiled mustache bindings
until the Vue instance is ready */

[v-cloak] {
  display: none;
}

* {
  margin: 0;
  padding: 0;
}

body {
  font: 15px/1.3 "Open Sans", sans-serif;
  color: #5e5b64;
  text-align: center;
}

a,
a:visited {
  outline: none;
  color: #389dc1;
}

a:hover {
  text-decoration: none;
}

section,
footer,
header,
aside,
nav {
  display: block;
}

/*-------------------------
    The order form
--------------------------*/

form {
  background-color: #61a1bc;
  border-radius: 2px;
  box-shadow: 0 1px 1px #ccc;
  width: 400px;
  padding: 35px 60px;
  margin: 50px auto;
}

form h1 {
  color: #fff;
  font-size: 64px;
  font-family: "Cookie", cursive;
  font-weight: normal;
  line-height: 1;
  text-shadow: 0 3px 0 rgba(0, 0, 0, 0.1);
}

form ul {
  list-style: none;
  color: #fff;
  font-size: 20px;
  font-weight: bold;
  text-align: left;
  margin: 20px 0 15px;
}

form ul li {
  padding: 20px 30px;
  background-color: #e35885;
  margin-bottom: 8px;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.1);
  cursor: pointer;
}

form ul li span {
  float: right;
}

form ul li.active {
  background-color: #8ec16d;
}

div.total {
  border-top: 1px solid rgba(255, 255, 255, 0.5);
  padding: 15px 30px;
  font-size: 20px;
  font-weight: bold;
  text-align: left;
  color: #fff;
}

div.total span {
  float: right;
}
</style>


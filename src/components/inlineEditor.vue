<template>
   
      <v-flex xs10 offset-xs1 grid-list-xl text-xs-center >
        <v-card dark color="dark">
          <v-card-text>
              <div id="main" v-cloak v-on:click="hideTooltip" >
       
       <div class="tooltip" v-on:click.stop v-if="show_tooltip">
           
     <input type="text" v-model="text_content"/>
    </div>

    <p v-on:click.stop="toggleTooltip">{{ text_content }}</p>
</div>
</v-card-text>
        </v-card>
      </v-flex>


</template>
<script>
export default {
    name : 'inlineEditor',
    data(){
        return{
            show_tooltip: false,
        text_content: 'Edit me.'

        }
    },methods :{
         hideTooltip: function(){
            // When a model is changed, the view will be automatically updated.
            this.show_tooltip = false;
        },
        toggleTooltip: function(){
            this.show_tooltip = !this.show_tooltip;
        }
    }
    
}
</script>
<style scoped>


[v-cloak] {
  display: none;
}

*{
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



.tooltip{
    background-color:#5c9bb7;

    background-image:-webkit-linear-gradient(to bottom, #5c9bb7, #5392ad);
    background-image:-moz-linear-gradient(to bottom, #5c9bb7, #5392ad);
    background-image:linear-gradient(to bottom, #5c9bb7, #5392ad);

    box-shadow: 0 1px 1px #ccc;
    border-radius:3px;
    width: 290px;
    padding: 10px;

    position: absolute;
    left:50%;
    margin-left:-150px;
    top: 80px;
}

.tooltip:after{
    
    content:'';
    position:absolute;
    border:6px solid #5190ac;
    border-color:#5190ac transparent transparent;
    width:0;
    height:0;
    bottom:-12px;
    left:50%;
    margin-left:-6px;
}

.tooltip input{
    border: none;
    width: 100%;
    line-height: 34px;
    border-radius: 3px;
    box-shadow: 0 2px 6px #bbb inset;
    text-align: center;
    font-size: 16px;
    font-family: inherit;
    color: #000000;
    font-weight: bold;
    outline: none;
}

p{
    font-size:22px;
    font-weight:bold;
    color:#6d8088;
    height: 30px;
    cursor:pointer;
}

p b{
    color:#ffffff;
    display:inline-block;
    padding:5px 10px;
    background-color:#c4d7e0;
    border-radius:2px;
    text-transform:uppercase;
    font-size:18px;
}

p:before{
    content:'✎';
    display:inline-block;
    margin-left:0px;
    font-weight:normal;
    vertical-align: text-bottom;
}

#main{
    height:300px;
    position:relative;
    padding-top: 150px;
}
</style>

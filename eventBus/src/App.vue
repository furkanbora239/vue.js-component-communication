<template>
<div>
  <h1>I'm learning eventBus</h1>
  <hr>
  <app-paranet>
  </app-paranet>
</div>
</template>

<script>
import parentVue from './componentler/parent.vue'
export default {
  components:{
    appParanet: parentVue
  }
}
</script>

<style>
body{
  background-color: black;
  color: beige;
}
h1{
  text-align: center;
  font-size: 60px;
  font-family: "Verdana";
}
h2{
  text-align: center;
  font-size: 50px;
}
h3{
  text-align: center;
  font-size: 40px;
}
div{
  width: 70%;
  margin: auto;
  padding: 5%;
  text-align: center;
}
input{
  border-radius: 7px;
  border: 0px;
  background-color: rgb(184, 169, 152);
  font-size: 35px;
  width: 75%;
  text-align: center;
}
p{
  text-align: center;
  border-style: solid;
  border-color: red;
  border-top: hidden;
  border-left: hidden;
  border-right: hidden;
  width: 60%;
  font-size: 24px;
  margin: auto;
  margin-bottom: 4%;
}
button{
  background-color: rgb(184, 169, 152);
  border: none;
  text-align: center;
  display: inline-block;
  font-size: 35px;
  border-radius: 7px;

}
.box{
    background-color: rgba(43, 42, 42, 0.603);
    border-radius: 10px;
    width: 90%;
}
</style>

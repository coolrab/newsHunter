<template>
  <div id="app">
    <Header />
    <Todos :todos_data = "todos"/>
    <StoryTemplate :todos_data = "todos"/>

  </div>
</template>

<script>
import Todos from "./components/Todos";
import StoryTemplate from "./components/StoryTemplate";
import Header from "./components/Header";
import axios from "axios";
export default {
	name: 'app',
	components: {
    Todos,
    StoryTemplate,
    Header
	},
	
data(){
	return{
		todos: []
	
	}
},

 created() {
 axios.get("http://158.39.77.36:5000/named_entity/retrieve?userid=abcd1234fedc0987&named_entityiri=http://www.wikidata.org/entity/Q129118")
 .then(res => this.todos = res.data)
 .catch(err => alert(err));
 }

// created(){
// 	{
//   // GET /someUrl
// 	this.$http.get('http://158.39.77.36:5000/named_entity/retrieve?userid=abcd1234fedc0987&named_entityiri=http://www.wikidata.org/entity/Q129118')
// 	.then(response => {
// 		console.log(response.data);
//     // get body data
//     this.todos = response.data;

//   }, response => {
//     alert ('response')
//   });
// }
// }

}
</script>


<style>

*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
	background: #1ab394;
  margin: 10px 10px;
	list-style: none;
	}
	a {
		text-decoration: none;
	}
	

</style>

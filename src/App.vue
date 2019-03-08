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
export default {
	name: 'app',
	components: {
    Todos,
    StoryTemplate,
    Header
	},
	
data(){
	return{
		todos: [{
	"named_entityiri": "http://www.wikidata.org/entity/Q59411480",
	"label": "Ballon d'Or F\u00e9minin",
	"type": "Event",
	"facts": [{
		"source": "https://www.wikidata.org/wiki/Q129118",
		"sourcelabel": "Wikidata",
		"map": [{
			"key": "Date",
			"keyiri": "http://www.w3.org/2001/XMLSchema#date",
			"value": "2018-12-03",
			"valuetype": "http://www.w3.org/2001/XMLSchema#date"
		}, {
			"key": "Location",
			"keyiri": "https://www.wikidata.org/wiki/Q2221906",
			"value": "Paris",
			"valueiri": "https://www.wikidata.org/wiki/Q90"
		}, {
			"key": "First awarded",
			"value": "2018",
			"valuetype": "http://www.w3.org/2001/XMLSchema#year"
		}, {
			"key": "Current holder",
			"value": "Ada Hegerberg",
			"valuetype": "https://www.wikidata.org/wiki/Q129118"
		}, {
			"key": "Presented by",
			"keyiri": "https://www.wikidata.org/wiki/Property:P1027",
			"value": "France Football",
			"valueiri": "https://www.wikidata.org/wiki/Q244750"
		}]
	}],
	"graph": {
		"title": "Knowledge graph for Ballon d'Or F\u00e9minin",
		"explanation": "This graph [will be] extracted by News Angler from reference and other data sources.",
		"nodes": [{
			"label": "Ballon d'Or F\u00e9minin",
			"nodeiri": "http://www.wikidata.org/entity/Q59411480"
		}, {
			"label": "France Football Federation",
			"nodeiri": "https://www.wikidata.org/wiki/Q244750"
		}],
		"edges": [{
			"from": "Ballon d'Or F\u00e9minin",
			"to": "France Football Federation",
			"edgelabel": "presented_by",
			"edgeiri": "https://www.wikidata.org/wiki/Property:P1027"
		}]
	},
	"status": 0
}]
	
	



		
	}
}


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

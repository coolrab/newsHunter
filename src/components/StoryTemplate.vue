<template>

<div class="main-form">
     
    <section class="start-button"  v-if="!showForm">
    <div class="story-button">
         <button id="button" @click.stop.prevent="showForm=true">
            Create a Story
        </button>

    </div>

    
    </section>
    
   
  <section class="top-container" v-if="showForm" >
    <div class="story-form">
       
      <form action="post">
        <label class="label" for="author">Author</label>
        <input class="inputs" type="text" name="author" value="Bjarte" v-model="author">
        <label class="label" for="title">Title</label>
        <input class="inputs" type="text" name="title" value=" Ballon d'Or twerking scandal" v-model="title">
        <label class="label" for="description">Description</label>
        <textarea name="description" class="inputs" v-model="description">
            Scandal ensued at the Ballon d'Or when Ada Hegerberg was asked by broadcast
            host Martin Solveig to twerk on stage.
        </textarea>
        <label class="label" for="newscodes">Newscodes</label>
        <textarea name="newscodes" class="inputs" v-model="newscodes">
          Sports, soccer
        </textarea>
        <label class="label" for="keywords">Keywords</label>
        <textarea name="keywords" class="inputs" v-model="keywords">
          
        </textarea>

        <!-- <div>
          <p>{{keywords}}</p>
        </div> -->
          <div :key="i" v-for="(item, i) in items">
            <p>{{item}}</p>
          </div>
        
          <button @click.stop.prevent="addKeywords" id="submit" class="btn">Submit</button>
        
      </form> 

      <ConceptPannel :todo="todos_data"/>
      
      <div class="closing-button">  
            <button id="close" class="btn" @click="showForm=false">
            X
        </button> 
        </div> 
    </div>

  
    </section>
   
  
  

</div>

    
</template>


<script>
import ConceptPannel from "./ConceptPannel";
export default {
  name: "StoryTemplate",
  props: ["todos_data"],
  components : {
      ConceptPannel,
      
  },
  
  data(){
      return{
          showForm:false,
        formId: 0,
        author:"",
        title:"",
        description:"",
        newscodes:"",
        keywords: "" ,
        items: [],
        
      }
  },

  methods: {
    addKeywords: function(){
      this.items.push({
        id: this.formId++,
        author: this.author,
        title: this.title,
        description: this.description,
        newscodes: this.newscodes,
        keywords: this.keywords
        
        })
      this.author= "";
      this.title= "";
      this.description= "";
      this.newscodes= "";
      this.keywords = "";
    }
  }
}
</script>

<style scoped>




.story-form {
box-shadow: 0 1px 5px rgba(104,104, 104, 0.8);
display: flex;
align-items: flex-start;
background: #ccc;
padding:10px 30px;
border-radius:8px;
margin: 20px 20px;
justify-content: space-between;

}

.story-form > form {
  display: grid;
  grid-template-columns: 1fr 5fr;
  grid-template-rows: 1fr 1fr 3fr 2fr 2fr;
  grid-gap: 10px;
 } 



#button{
padding: 0.6rem 1.3rem;
  margin: 20px;
  cursor: pointer;
  font-size: 24px;
  font-weight: bold;
  min-width: 400px;
  min-height: 50px;
  
  
}

#button:hover{
  background: hotpink;
  color: aqua;
}

.btn {
  padding: 0.6rem 1.3rem;
  margin: 10px 10px;
  cursor: pointer;
  font-size: 16px;
  
}

.btn:hover {
  background: #1ab394;
}

#close{
    float: right;
}

.label {
  display: flex;
  align-items: center;
  font-weight: 600;
  font-size: 1.2rem;
}

.inputs {
  font-family: inherit, sans-serif;
  outline: 1; 
   background: #f4f4f4;
  width: 100%; 
  
  margin: 0 0 15px; 
   padding: 15px; 
  box-sizing: border-box;
  font-size: 14px;
  border-radius: 10px;
  background: rgba(255, 255, 255, 0.8);
}


</style>


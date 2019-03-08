 <template>

    
    <div class="concept-pannel" >
      <div class="element" >
        
         <span>People:</span>
        <ul>
          <!-- <li><a :href="todo.named_entityiri">{{todo.label}}</a></li> -->
        </ul>
      </div>

      
      

      <!-- <div class="element">
        <span>Event:</span>
        <ul>
          <li><a :href="link">{{todo.facts[0].map[1].value}}</a></li> -->
          <!-- <li>{{link}</li> 
          <li><a href=""></a></li>
        </ul>
       -->


      <div  class="items" :key="index" v-for = "(value, index) in values">
          <!-- <ul :key="index" v-for = "({map:data}, index) in value">{{data}}</ul>  -->
          
          <ul><a :href="value.keyiri"></a>{{value.key}}</ul>
          
         <!-- <ul :key="index" v-for = "({data:key}, index) in data"><a :href="key.keyiri">{{key}}</a></ul>  -->
         <!-- <p><a :href="value.named_entityiri">{{value.facts[0].map}}</a></p> -->
         <!-- <ul :key="index" v-for = "({map:data}, index) in value">{{data}}</ul> -->
          <li class="list-element"><a  :href="value.valuetype||value.valueiri">{{value.value}}</a> </li>
          <button id="delete-btn">X</button>
         
          
      </div>
    <hr>
    <hr>
      {{value}}
  
      <button @click="setCurrent" id="submit" class="btn">Fetch</button>
    </div> 

  
 </template>

 <script>
 export default {
     name: "ConceptPannel",
     props:["todo"],
     data(){
       return{
          values: null,
          value: this.value
       }
     },
     methods: { 
       setCurrent: function(){
         this.values = this.todo;

       },
           
         
       }
     }
 
 </script>

 <style scoped>
 .concept-pannel {
  box-sizing: border-box;
   max-width: 30%;
   padding: 25px;
   background-color: #ddd;
   margin-left: 10px;
   border-radius: 5px;
   min-height: 620px;
   
 }

.items{
  font-size: 16px;
   font-weight: bold;
}

.items ul {
   list-style: none;
   background: rgb(116, 114, 114);
   color: white;
   text-align: left;
   display: block;
   margin: 5px 10px 2px 0;
   padding: 5px 5px;
   border-radius: 5px;
   cursor: pointer;
   font-size: 16px;
 }

.list-element {
  background: #f4f4f4;
  padding: 10px;
  border: 2px #ccc;
  padding: 15px 25px;
  margin: 20px, 20px;
  border-radius: 10px;
  font-size: 20px;
}

 .items ul:hover{
   background: #1ab394;
 }
 


 	
  a:link {
  color:#1ab394;
}
  a:hover {
   background: rgb(231, 192, 212);
   font-weight: 900;
 }

 .btn {
  padding: 0.6rem 1.3rem;
  margin: 10px 10px;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
  float:right;
  width: 100%;
  
  
}

.btn:hover{
  background: #1ab394;
}

#delete-btn{
  float: right;
  border-radius: 80px;
  font-weight: 900;
  color: red;
  padding: 2px 5px;
  cursor: pointer;
}

#delete-btn:hover{
background:#1ab394;
}

 </style>

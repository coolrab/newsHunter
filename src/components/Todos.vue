<template>
   <div>
       <h1>{{todos_data.label}}</h1>
       <h1>{{todos_data.graph.title}}</h1>
       </div> 
</template>


<script>
export default {
   name: "Todos",
   props: ["todos_data"] 
}
</script>

<style scoped>

</style>

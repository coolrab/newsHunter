<template>
  <div>
    <h1>{{todos_data[0].label}}</h1>
    <h1>{{todos_data[0].graph.title}}</h1>
  </div>
</template>


<script>
export default {
  name: "Todos",
  // todos_data is the single prop passed to this component from the parent.
  // it is of type Array, with a single Object inside. So we can either do this:
  // props: ["todos_data"]
  // or we could do this:
  props: {
    todos_data: Array
  }
  // the benefit of the latter is that it makes clear, WITHIN the component, that an array is expected.
  // Then you know you will need to use an index to access the content -- and then you can start using
  // keys on that object :)
  // you could even do the following, if the component won't function without the todos_data prop:
  //   props: {
  //      todos_data: {
  //         type: Array,
  //         required: true
  //      }
  //   }
};
</script>

<style scoped>
</style>

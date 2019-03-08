<template>
    <nav class="header">
        
        <h2>News Hunter </h2> 
        <h4>WTNews</h4>
    </nav>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style scoped>
.header{
    background: #333;
    color: #fff;
    text-align: center;
    /* padding: 10px; */
        padding: 0.3rem 1rem;
    display: flex;
    text-align: center;
    justify-content: center;
}

.header a {
    color: #fff;
    padding-right: 5px;
}
h2 {
    display: block;
    font-size: 1.5em;
    margin-block-start: 0.83em;
    margin-block-end: 0.83em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
}

 h4 {
display: block;
    margin-block-start: 1.33em;
    margin-block-end: 1.33em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;

 }
    
</style>

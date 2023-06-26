<template>
    <div>
       <h1>List of students</h1>
       <br/>
       <div v-for="person in people" :key="person.id" class="container">
        <div class="card">
            <h1>{{person.name}} {{person.surname}}</h1>
            <p>Age: {{person.age}} <br> Gender: {{person.gender}}</p>
        </div>
           
       </div>
    </div>
</template>

<script>
   export default {
    data() {
      return {
        people: [],
      };
    },
    mounted() {
      fetch('https://smasherk.github.io/jsonServer/server.json')
        .then(response => response.json())
        .then(data => {
          this.people = data;
        });
    },
};


</script>

<style  scoped>
.container{
    display: inline-flex;
    flex-wrap: wrap;
}
.card{
    margin: 2rem ;
    padding:0  1rem 1rem;
    border: 1px solid black;
    border-radius: .5rem;
}

</style>
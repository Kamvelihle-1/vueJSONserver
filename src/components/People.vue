<template>
    <div>
       <h1>List of students</h1>
       <br/>
       <div v-for="person in people" :key="person.id">
            <p>Name: {{person.name}}</p>
            <p>Surname: {{person.surname}}</p>
            <p>Age: {{person.age}}</p>
            <p>Gender: {{person.gender}}</p>
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

</style>
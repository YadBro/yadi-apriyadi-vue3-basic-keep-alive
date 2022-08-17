<template>
  <b-card>
    <p>Ini adalah post</p>
    <b-list-group>
      <b-list-group-item v-for="(people, index) in peoples" :key="index">
        {{people.name}}
      </b-list-group-item>
    </b-list-group>
  </b-card>
</template>

<script>
  export default {
    data() {
      return {
        peoples: [],
      }
    },
    async created() {
      const response = await fetch('https://swapi.dev/api/people');
      const data = await response.json();
      this.peoples = data.results;
    },
  }
</script>
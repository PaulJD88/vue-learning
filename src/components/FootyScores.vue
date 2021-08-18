<template>
  <div class="hello">
    <h1>Footy Scores</h1>
    <button @click="getScores">Get Scores</button>
    <img v-for="team in teams" :key="team.team.id" :src="team.venue.image">
  </div>
</template>

<script>
export default {
  name: "FootyScores",
  data() {
    return {
      images: [
        "https://placekitten.com/408/286",
        "https://placekitten.com/200/139",
        "https://placekitten.com/200/287",
      ],
      teams: []
    };
  },
  methods: {
    getScores() {
      console.log("Getting Scores");
      fetch(
        "https://api-football-beta.p.rapidapi.com/teams?league=39&season=2021",
        {
          method: "GET",
          headers: {
            "x-rapidapi-key":
              "68ae882537mshb820981746e1d9dp1355efjsnfbbca5951726",
            "x-rapidapi-host": "api-football-beta.p.rapidapi.com",
          },
        }
      )
        .then(function(response) { return response.json(); })
        .then((data) => {
          console.log(data.response);
          this.teams = data.response;
          console.log(this.teams[0].team.logo)
        })
        .catch((err) => {
          console.error(err);
        });
    },
  },
};
</script>

<style scoped>
ul {
  color: purple;
}
</style>

<template>
  <div class="hello">
    <h1>Footy Scores</h1>
    <button @click="getScores">Get Scores</button>
    <div class="teamcard" v-for="team in teams" :key="team.team.id">
      <div class="logoName">
        <img class="logo" :src="team.team.logo" />
        <h2>{{ team.team.name }}</h2>
        <h5>Founded - {{ team.team.founded }}</h5>
      </div>
      <div class="imageContainer">
        <img class="venue" :src="team.venue.image" />
        <h3>
          {{ team.venue.name }}
          (Capacity:{{ team.venue.capacity }})
        </h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FootyScores",
  data() {
    return {
      teams: [],
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
        .then(function (response) {
          return response.json();
        })
        .then((data) => {
          console.log(data.response);
          this.teams = data.response;
          console.log(this.teams[0].team.logo);
        })
        .catch((err) => {
          console.error(err);
        });
    },
  },
};
</script>

<style scoped>
.teamcard {
  display: flex;
  flex-direction: column;
  flex: flex-wrap;
  border: solid black;
  border-radius: 25px;
  margin-bottom: 5px;
  background-color: beige;
  width: 70%;
  height: auto;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}
.logo {
  width: 20%;
  height: 20%;
}
h2 {
  color: black;
}
h5 {
  color: black;
}
h3 {
  transition: 0.5s ease;
  opacity: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  font-size: 20px;
  background-color: white;
  font-family: "Courier New", Courier, monospace;
  border-radius: 5px;
  padding: 16px 32px;
}
.imageContainer {
  position: relative;
  width: 50%;
}
.imageContainer:hover .venue {
  opacity: 0.3;
}
.venue {
  opacity: 1;
  width: 100%;
  height: auto;
  transition: 0.5s ease;
  backface-visibility: hidden;
  border-radius: 25px;
}
.imageContainer:hover h3 {
  opacity: 1;
}
subtitle {
  color: black;
}
</style>

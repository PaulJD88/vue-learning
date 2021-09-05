<template>
  <div class="hello">
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
  name: "PremierLeague",
  data() {
    return {
      teams: [],
    };
  },
  methods: {
    getScores() {
      console.log("PremierLeague");
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
  mounted: function () {
    this.getScores();
  },
};
</script>

<style scoped>
* {
  box-sizing: border-box;
}
.hello {
  flex-wrap: wrap;
  display: flex;
  flex-direction: row;
  width: auto;
  height: 100%;
  padding: 50px 50px 50px 50px;
  margin: 10px;
}
@media (max-width: 800px) {
  .hello {
    flex-direction: column;
  }
}
.teamcard {
  border: solid black;
  margin: 5px 0px 5px 0px;
  border-width: 4px;
  background-color: #a64f0383;
  border-radius: 5px;
  width: 50%;
  height: auto;
  padding: 15px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}
.logoName {
  border: solid black;
  border-top: 2px;
  border-right: 2px;
  border-left: 2px;
}
.logo {
  padding: 8px;
  width: 25%;
  height: 25%;
}
h2 {
  display: flex;
  justify-content: center;
  color: black;
  text-decoration: underline;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 30px;
}
h5 {
  color: black;
  font-size: 15px;
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
.imageContainer:hover h3 {
  opacity: 1;
}
.imageContainer {
  position: relative;
  width: 100%;
}
.venue {
  opacity: 1;
  width: 100%;
  height: auto;
  transition: 0.5s ease;
  backface-visibility: hidden;
}
.imageContainer:hover .venue {
  opacity: 0.3;
}
</style>

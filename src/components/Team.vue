<template>
  <div class="hello">
  <p> {{team}} </p>
  </div>
</template>

<script>
export default {
  name: "FootyScores",
  data() {
    return {
      team: {

      },
    };
  },
  methods: {
    getTeam() {
      console.log("Getting Scores");
      fetch(
        "https://api-football-beta.p.rapidapi.com/teams/statistics?season=2021&team=33&league=39",
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
          this.team = data.response;
          console.log(this.teams[0].team.logo);
        })
        .catch((err) => {
          console.error(err);
        });
    },
  },
  mounted: function () {
    this.getTeam()
  }
};
</script>

<style scoped>
.teamcard {
  display: flex;
  flex-direction: column;
  border: solid black;
  border-width: 5px;
  margin-bottom: 25px;
  background-image: linear-gradient(to bottom right, purple, pink, white);
  border-radius: 2px;
  width: 100%;
  height: auto;
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
button {
  margin-bottom: 10px;
}
</style>

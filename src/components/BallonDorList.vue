<template>
  <h1>Ballon D'or List</h1>
  <div class="container">
    <div
      v-for="player in players"
      :key="player.name + player.year"
      class="player-tile"
    >
      <img :src="player.picture" alt="Player Image" />
      <div class="info">
        <p>{{ player.name }}</p>
        <p>Age: {{ player.age }}</p>
        <p>Year: {{ player.year }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import playersData from "../data/ballonDor.json";

export default {
  setup() {
    return {
      players: playersData.players,
    };
  },
};
</script>

<style scoped>
h1 {
  text-align: center;
  margin-bottom: 100px;
}
.container {
  display: flex;
  width: 100%;
  flex-wrap: wrap;
  justify-content: space-around;
}

.container img {
  width: 200px;
  height: 200px;
}

.player-tile {
  position: relative;
  width: 200px;
  height: 200px;
  margin: 10px;
  background-size: cover;
  background-position: center;
}

.player-tile .info {
  position: absolute;
  width: 100%;
  bottom: 0;
  left: 0;
  padding: 10px;
  color: white;
  background-color: rgba(0, 0, 0, 0.5);
}
</style>

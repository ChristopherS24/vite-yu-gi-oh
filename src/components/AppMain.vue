<script>
import axios from 'axios';

export default {
  data() {
    return { 
      characters: []      
    }
  },
  created() {
    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0')
      .then((res) => {
        this.characters = res.data.data;
      });
  }
}
</script>

<template>
  <main>
    
    <div class="container">

        <!--<select name="archetype" id="archetype">
        </select>-->
        <input type="archetype">

      <div class="row-select">
        <h2>founded</h2>
      </div>

      <div class="row">
        <div class="card-container">
          <div v-for="(character, i) in characters" :key="i" class="card">
            <div class="text-center">
              <img :src="character.image" :alt="character.name">
            </div>
            <h2>
              {{ character.name }}
            </h2>
            <h3>
              {{ character.archetype }}
            </h3>
          </div>
        </div>
      </div>

    </div>

  </main>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;

main .container {
  background-color: rgb(162, 6, 6);
}

.row-select {
  background-color: black;
  color: white;
}

</style>

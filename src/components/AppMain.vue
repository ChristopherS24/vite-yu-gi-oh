<script>
import axios from 'axios';

export default {
  data() {
    return { 
      
    }

  },
  created() {
    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then((res) => {
        this.characters = res.data.data;
      });
  }
}
</script>

<template>
  <main>
    
    <div class="container">

      <div class="row-select">
        <!--<select name="archetype" id="archetype">
          
        </select>-->

        <input type="archetype">
      </div>

      <div class="row">
        <div >
          main
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

</style>

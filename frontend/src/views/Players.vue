<template>
  <div class="players">
    <div class="columns is-multiline">
      <div class="column is-12">
        <h2 class="is-size-2 has-text-centered">Список игроков</h2>
      </div>

      <PlayerBox
        v-for="player in players"
        :key="player.id"
        :player="player"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";

import PlayerBox from "@/components/PlayerBox.vue";

export default {
  name: 'Players',
  data () {
    return {
      players: [],
    }
  },
  components: {
    PlayerBox
  },
  mounted() {
    this.getPlayers()

    document.title = 'Список игроков'
  },
  methods: {
    async getPlayers() {
      await axios
          .get(`/api/players/`)
          .then(response => {
            this.players = response.data
          })
          .catch(error => {
            console.log(error)
          })
    }
  }
}

</script>
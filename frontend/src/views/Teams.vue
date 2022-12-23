<template>
  <div class="teams">
    <div class="columns is-multiline">
      <div class="column is-12">
        <h2 class="is-size-2 has-text-centered">All Teams</h2>
      </div>

      <TeamBox
          v-for="team in teams"
          :key="team.key"
          :team="team"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";

import TeamBox from "@/components/TeamBox.vue";

export default {
  name: 'Teams',
  data () {
    return {
      teams: [],
    }
  },
  components: {
    TeamBox
  },
  mounted() {
    this.getTeams()

    document.title = 'Teams'
  },

  methods: {
    async getTeams() {
      await axios
          .get(`/api/teams/`)
          .then(response => {
            this.teams = response.data
          })
          .catch(error => {
            console.log(error)
          })
    }
  }
}
</script>


<template>
  <div class="column is-3">
    <div class="box">
      <figure class="image mb-4">
        <img :src="player.get_player_thumbnail" alt="Player Thumbnail">
      </figure>

      <h3 class="is-size-6">{{ player.get_player_full_name }}</h3>
      <p class="is-size-8 has-text-grey">{{ player.get_player_team }}</p>

      <router-link :to="player.get_absolute_url" class="button is-dark mt-4">View Details</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PlayerBox',
  props: {
    player: Object
  }
}
</script>


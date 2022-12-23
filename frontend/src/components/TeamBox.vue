<template>
  <div class="column is-3">
    <div class="box">
      <figure class="image mb-4" >
        <img :src="team.get_team_thumbnail" alt="Team Thumbnail">
      </figure>

      <h3 class="is-size-6">{{ team.name }}</h3>
      <p class="is-size-8 has-text-grey">{{ team.location }}</p>

      <router-link :to="team.get_absolute_url" class="button is-dark mt-4">View Details</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TeamBox',
  props: {
    team: Object
  }
}
</script>
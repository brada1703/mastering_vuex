<template>
  <div>
    <h1>Create an event, {{ user.name }}</h1>
    <p>This event was created by {{ user.name }}</p>
    <ul>
      <li v-for="cat in categories" :key="cat">{{ cat }}</li>
    </ul>
    <p>There are {{ catLength }} categories</p>
    <!-- <p>{{ getEvent(1) }}</p> -->
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  computed: {
    catLength() {
      // return this.$store.categories.lenth
      return this.$store.getters.catLength
    },
    // getEvent() {
    //   return this.$store.getters.getEventById
    // },
    ...mapState(['user', 'categories'])
  }

  // another example:
  // computed: mapState({
  //   user: 'user',
  //   categories: 'categories'
  // })
  // another example:
  // computed: mapState({
  //   userName: state => state.user.name,
  //   userID: state => state.user.id,
  //   categories: state => state.categories
  // })
  // another example:
  // computed: {
  //   userName() {
  //     return this.$store.state.user.name
  //   },
  //   userID() {
  //     return this.$store.state.user.id
  //   }
  // }
}
</script>

<style scoped>
</style>
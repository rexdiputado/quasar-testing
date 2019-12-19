<template>
  <q-page>
    <!-- <img alt="Quasar logo" src="~assets/quasar-logo-full.svg"> -->
    <q-list bordered>
      <q-item
        clickable
        v-ripple
      >
        <q-item-section avatar>
          <q-avatar size="70px">
            <img src="https://cdn.quasar.dev/img/boy-avatar.png">
          </q-avatar>
        </q-item-section>
        <q-item-section>Image avatar</q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  created () {
    this.$axios.get('https://www.reddit.com/r/aww.json?raw_json=1')
      .then(response => {
        this.posts = response.data.data.children
      })
      .catch(error => {
        console.log(error)
      })
  },
  data () {
    return {
      posts: []
    }
  }
}
</script>

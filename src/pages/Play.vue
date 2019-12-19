<template>
<q-page padding>
    <div class="row q-gutter-xl">
      <div class="col">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum qui voluptatum laborum quasi repudiandae ad sed, doloremque, omnis, accusamus sit consequuntur magni fugit ut explicabo veritatis aliquid. At, magnam dicta!
        <div>
          <q-btn color="teal" @click="showLoading" label="Show Loading" />
          <q-btn color="primary" label="Primary" @click="handleClick"/>
          <q-input outlined v-model="myInput" label="Outlined" />
        </div>
        <p v-for="n in 40" :key="n">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugit nihil praesentium molestias a adipisci, dolore vitae odit, quidem consequatur optio voluptates asperiores pariatur eos numquam rerum delectus commodi perferendis voluptate?
        </p>

        <!-- place QPageScroller at end of page -->
        <q-page-scroller position="bottom-right" :scroll-offset="150" :offset="[18, 18]">
          <q-btn fab icon="keyboard_arrow_up" color="accent" />
        </q-page-scroller>
      </div>
      <div class="col">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Exercitationem ullam aspernatur beatae quia repellendus est, architecto ut asperiores nesciunt nihil dignissimos! Facilis esse fugit molestias sunt, consequatur quis placeat neque.
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      myInput: ''
    }
  },
  methods: {
    handleClick () {
      this.myInput = 'clicked'
    },
    showLoading () {
      this.$q.loading.show({
        message: 'Some important <b>process</b> is in progress.<br/><span class="text-primary">Hang on...</span>'
      })

      // hiding in 3s
      this.timer = setTimeout(() => {
        this.$q.loading.hide()
        this.timer = void 0
      }, 3000)
    }
  }
}
</script>

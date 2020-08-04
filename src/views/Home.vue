<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld :msg="mens" @custom-event="onChangeMsg"/>
    <p>{{ jwt }}</p>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  created() {
    console.log('teste', this.$route.meta)
  },
  computed: {
    jwt() {
      console.log(this.$route.query.name)
      return this.$route.query.name 
    }
  },
  components: {
    HelloWorld
  },
  data() {
    return {
      mens: 'André'
    }
  },
  methods: {
    onChangeMsg(value) {
      this.mens = `Hello, ${value}`
    }
  }
}
</script>

<template>
  <div>
    {{ msg }}
    <input type="button" value="show noti" @click="showNotification">
  </div>
</template>

<script>
export default {
  name: 'notifications',
  data () {
    return {
      msg: 'Todo!!'
    }
  },
  methods: {
    showNotification: function () {
      console.log('TODO')
    }
  },
  created () {
    if (!('Notification' in window)) {
      alert('This browser does not support system notifications')
    }
    Notification.requestPermission().then(function (result) {
      console.log(result)
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

<template>
  <div>
    <date-picker />
    <main-menu />
  </div>

</template>

<script>
import MainMenu from 'components/MainMenu'
import datePicker from 'components/datePicker'

export default {
  name: 'MainLayout',
  components: {
    MainMenu,
    datePicker

  },
  data () {
    return {}
  }
}
</script>

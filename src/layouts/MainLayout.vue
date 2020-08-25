<template>
  <div>
    <date-picker />
    <div>Your Balance</div>
    <main-menu />
    <card-list-carousel />
  </div>

</template>

<script>
import MainMenu from 'components/MainMenu'
import datePicker from 'components/datePicker'
import cardListCarousel from 'components/cardListCarousel'

export default {
  name: 'MainLayout',
  components: {
    MainMenu,
    datePicker,
    cardListCarousel

  },
  data () {
    return {}
  }
}
</script>

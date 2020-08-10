<template>
  <div class="row main-menu">
    <div class="col-2 vertically-center">
      <q-icon name="o_home" class="main-menu__icon "/>
    </div>
    <div class="col-2 vertically-center">
      <q-icon name="o_account_balance_wallet" class="main-menu__icon "/>
    </div>
    <div class="col-4">
      <div class="main-menu__half-circle"></div>
      <q-icon name="0_add_box" class="main-menu__center"/>
    </div>
    <div class="col-2 vertically-center">
      <q-icon name="o_pie_chart" class="main-menu__icon"/>
    </div>
    <div class="col-2 vertically-center">
      <q-icon name="o_settings" class="main-menu__icon"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainMenu'
}
</script>

<style lang="scss" scoped>
.vertically-center {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>

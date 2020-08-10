<template>
  <div class="row main-menu">
    <div class="col-2 text-center">
      <q-icon name="o_home" class="main-menu__icon "/>
    </div>
    <div class="col-2 text-center">
      <q-icon name="o_account_balance_wallet" class="main-menu__icon "/>
    </div>
    <div class="col-4">
      <div class="main-menu__half-circle"></div>
      <q-icon name="0_add_box" class="main-menu__center"/>
    </div>
    <div class="col-2 text-center">
      <q-icon name="o_pie_chart" class="main-menu__icon"/>
    </div>
    <div class="col-2 text-center">
      <q-icon name="o_settings" class="main-menu__icon"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainMenu'
}
</script>

<style scoped lang="scss">

.main-menu {
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 70px;
  padding: 0 15px;
  background-color: #FFFFFF;

  &__icon {
    font-size: 2rem;
    color: #A6AAB4;
  }

  &__center {
    position: absolute;
    top: -23px;
    left: 117px;
    color: #613EEA;
    font-size: 2.5rem;

    &::before {
      content: '';
      position: absolute;
      border: 2px solid #613eea;
      border-radius: 50%;
      left: 24px;
      top: -19px;
      width: 70px;
      height: 70px;
    }
  }

  &__half-circle {
    width: 70px;
    height: 70px;
    border: 10px solid #F9FAFB;
    background-color: #F9FAFB;
    border-radius: 50%;
    border-bottom-color: transparent;
    border-left-color: transparent;
    transform: rotate(135deg);
    position: absolute;
    top: -30px;
    left: 144px;

  }
}

</style>

<template>
  <div class="q-pa-md">
    <q-carousel
      v-model="slide"
      transition-prev="slide-right"
      transition-next="slide-left"
      swipeable
      animated
      padding
      arrows
      control-color="primary"
      class="rounded-borders"
      height="30vh"
    >
      <q-carousel-slide name="style" class="column no-wrap flex-center">
        <div class="text-center">
          <q-card class="user-card">
            <q-card-section class="h-100">
              <q-icon name="fab fa-cc-visa" class="user-card__logo" color="grey-4" size="lg"/>
              <h6 class="q-ma-none">Bank Mandiri</h6>
              <div class="user-card__number text-subtitle2">{{ userNumber | convertCardNum }}</div>
              <div class="user-card__holder text-subtitle2">{{ userCardHolder }}</div>
              <div class="user-card__expired">
                <div class="text-subtitle2">Exp: {{ userExpired }}</div>
              </div>
            </q-card-section>
          </q-card>
        </div>
      </q-carousel-slide>
    </q-carousel>
  </div>
</template>

<script>
import globalMixin from 'src/mixins/globalMixins'

export default {
  name: 'cardListCarousel',
  mixins: [globalMixin],
  data () {
    return {
      slide: 'style',
      userNumber: '1234123412341234',
      userCardHolder: 'John Doe',
      userExpired: '17/22'
    }
  }
}
</script>

<style lang="scss" scoped>
@import "src/css/mixin";

.user-card {
  width: 80vw;
  height: 25vh;
  position: relative;
  filter: drop-shadow(0px 8px 8px rgba(134, 118, 251, 0.6));
  background: linear-gradient(109.55deg, #8676FB 0%, #AB7BFF 100%);
  border-radius: 6px;
  color: white;

  &__logo {
    position: absolute;
    right: 15px;
    bottom: 10px;
  }

  &__number {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    @include linear-gradient-purple(168.55deg)
  }

  &__holder {
    position: absolute;
    bottom: 10px;
    @include linear-gradient-purple(168.55deg)
  }

  &__expired {
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translate(-50%, -50%);
  }
}

</style>

<template>
  <div class="q-pa-md">
    <q-layout>
      <q-page-container>
        <div class="text-weight-bolder text-h6">Daily transaction</div>
        <div class="flex justify-between">
          <div v-for="(item, index) in oneWeek" :key="index" class="q-mt-sm q-mr-xs inline-block">
          <span class="q-ml-sm">
           {{ item.day | convertDay }}
          </span>
            <div :class="item.date === date ? 'datePicker__circle active' : 'datePicker__circle'">
              {{ item.date }}
            </div>
          </div>
        </div>
      </q-page-container>
    </q-layout>
  </div>
</template>

<script>
import globalMixin from '../mixins/globalMixins'
export default {
  name: 'dateePicker',
  mixins: [globalMixin],
  data () {
    return {
      date: null,
      oneWeek: []
    }
  },
  created () {
    const num = [4, 3, 2, 1, 0, -1, -2]
    for (const i of num) {
      if (i >= 0) {
        this.dateNow(i, true)
      } else {
        this.dateNow(Math.abs(i), false)
      }
    }
  },
  methods: {
    dateNow: function (days, minus) {
      const now = new Date()
      this.date = now.getDate()
      const minDate = minus ? new Date(now.getTime() - (days * 24 * 60 * 60 * 1000)) : new Date(now.getTime() + (days * 24 * 60 * 60 * 1000))
      const dayName = minDate.getDay()
      const date = minDate.getDate()
      const dataObj = {
        day: dayName,
        date: date
      }
      this.oneWeek.push(dataObj)
    }
  }
}
</script>

<style lang="scss" scoped>
.datePicker {
  &__circle {
    width: 40px;
    height: 40px;
    background-color: #a6aab43d;
    text-align: center;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}

.active {
  background-color: rgb(97, 62, 234);
  color: white;
}

</style>

<template>
  <div class="q-pa-md">
    <q-layout>
      <q-page-container>
        <div class="text-weight-bolder text-h6">Daily transaction</div>
        <div class="q-mt-sm">
          <span class="q-ml-sm" v-for="(item, index) in oneWeek" :key="index">
            {{ item.day }}
          </span>
          <div class="datePicker__circle" v-for="(item, index) in oneWeek" :key="index">
            {{ item.date }}
          </div>
        </div>
      </q-page-container>
    </q-layout>
    <!--    <q-date-->
    <!--      v-model="date"-->
    <!--      first-day-of-week="1"-->
    <!--      today-btn-->
    <!--    />-->
  </div>
</template>

<script>
export default {
  name: 'dateePicker',
  data () {
    return {
      date: '2020/08/11',
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
  }
}

</style>

<template>
  <div>
    <section>
      <h2>Введите дату своего рождения:</h2>
      <div class="form-group__container">
        <div class="form-group">
          <div class="datePicker">
            <span>
              <select id="day" name="day">
                <option v-for="day of dayOfMonth" :key="day">{{ day }}</option>
              </select>
            </span>
            <span>
              <select id="month" name="month" v-model="selectMonth">
                <option v-for="month of mounts" v-bind:value="month">
                  {{ month }}
                </option>
              </select>
              <div>
                 <span>Выбрано: {{ selectMonth }}</span>
              </div>
            </span>
            <span>
              <select id="year" name="year" @change="populateYears()">
                <option v-for="year of  years" :key=" year" v-if="year >= 1900">{{ year }}</option>
              </select>
            </span>
            <div>
              <span>Выбрано: {{ years }}</span>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
let datePicker = document.querySelector('.datePicker'),
    yearSelect = document.querySelector('#year'),
    mountsSelect = document.querySelector('#month'),
    daySelect = document.querySelector('#day'),
    previousDay = null;

// datePicker.style.display = "none";
export default {
  name: "VDateOfBirdth",
  data: () => ({
    dayOfMonth: null,
    mounts: ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"],
    years: new Date().getFullYear(),
    selectMonth: ''
  }),
  methods: {
    populateYears(start, stop) {
      return new Array(stop - start).fill(start).map((n, i) => n + i)
    },
    checkMonth() {
      console.log(this.selectMonth)
    }
  },
  computed: {
    populateDays() {
      let month = this.selectMonth

      if (month === 'January' || month === 'March' || month === 'May' || month === 'July' || month === 'August' || month === 'October' || month === 'December') {
        this.dayOfMonth = 31
      } else if (month === 'April' || month === 'June' || month === 'September' || month === 'November') {
        this.dayOfMonth = 30
      } else {
        let year = yearSelect.value()
        let leap = (year % 4 === 0 && year % 100 !== 0) || year % 400 === 0;
        this.dayOfMonth = leap ? 29 : 28;
      }
      return month
    }
  }

}
</script>

<style scoped>

</style>
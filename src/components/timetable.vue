<template>
  <table class="table">
    <thead>
      <tr>
        <div class="card day d-inline-block" v-for="day in 6" v-bind:key="day" style="width: 15rem">
          <div class="card-body">
            <h5 class="card-title">{{ week[(date.getDay() - 1) + day] }}</h5>
            <p class="card-text">{{ date.getDate() + day }}</p>
          </div>
        </div>
      </tr>
    </thead>
    <tbody>
      <tr class="d-inline-block" v-for="schoolDay in timetable[0]" v-bind:key="schoolDay">
        <div class="card" v-for="subject in schoolDay" v-bind:key="subject" style="width: 15rem;">
          <div class="card-body">
            <h5 class="card-title">{{ subject.title }}</h5>
            <p class="card-text">{{ subject.cabinet }} {{ subject.teacher }}</p>
          </div>
        </div>
      </tr>
    </tbody>
  </table>

  <hr>

  <div class="timelesson-main-div">
    <div class="timelesson-blocks-div d-inline-block" style="width: 15rem; margin: 0; padding: 0;" v-for="dayTimeLesson in timelesson[0]" v-bind:key="dayTimeLesson">
      <div class="card" style="height: 6rem">
        <p class="card-text" style="margin-top: 2rem;">{{ dayTimeLesson.start }} → {{ dayTimeLesson.end }}</p>
      </div>
    </div>
  </div>
</template>

<script>
module.exports = {
  data: function () {
    return {
      date: new Date(),
      week: ["Mo", "Tu", "We", "Th", "Fr", "Sa", "Su"],

      timetable: [{
        Mo: [
          { title: 'Physics', cabinet: 35, teacher: 'Ведерникова С.В.'}, 
          { title: 'IT', cabinet: 40, teacher: 'Завъялова А.Н.' }, 
          { title: 'Social Studies', cabinet: 35, teacher: 'Свинкина И.А.' }, 
          { title: 'PE', cabinet: 'Спортзал', teacher: 'Зиненко Т.В.' }, 
          { title: 'English', cabinet: 35, teacher: 'Долгополова Э.В.' }, 
          { title: 'LSF', cabinet: 35, teacher: 'Осьмирко А.Е.' }],
        Tu: [
          { title: 'Math', cabinet: 35, teacher: 'Ведерникова С.В.'}, 
          { title: 'Math', cabinet: 35, teacher: 'Ведерникова С.В.' }, 
          { title: 'Physics', cabinet: 35, teacher: 'Ведерникова С.В.' }, 
          { title: 'IT', cabinet: 40, teacher: 'Завъялова А.Н.' }, 
          { title: 'History', cabinet: 35, teacher: 'Свинкина И.А.' }, 
          { title: 'English', cabinet: 35, teacher: 'Долгополова Э.В.' }],
        We: [
          { title: 'Physics', cabinet: 35, teacher: 'Ведерникова С.В.'}, 
          { title: 'IT', cabinet: 40, teacher: 'Завъялова А.Н.' }, 
          { title: 'Russian', cabinet: 35, teacher: 'Лукашевская Я.Н.' }, 
          { title: 'Russian', cabinet: 35, teacher: 'Лукашевская Я.Н.' }, 
          { title: 'Literature', cabinet: 35, teacher: 'Лукашевская Я.Н.' }, 
          { title: 'PE', cabinet: "Спортзал", teacher: 'Зиненко Т.В.' }],
        Th: [
          { title: 'Math', cabinet: 35, teacher: 'Ведерникова С.В.'}, 
          { title: 'Math', cabinet: 35, teacher: 'Ведерникова С.В.' }, 
          { title: 'Physics', cabinet: 35, teacher: 'Ведерникова С.В.' }, 
          { title: 'Physics', cabinet: 35, teacher: 'Ведерникова С.В.' }, 
          { title: 'Literature', cabinet: 35, teacher: 'Лукашевская Я.Н.' }, 
          { title: 'History', cabinet: 35, teacher: 'Свинкина И.А.' }],
        Fr: [
          { title: 'Math', cabinet: 35, teacher: 'Ведерникова С.В.'}, 
          { title: 'Math', cabinet: 35, teacher: 'Ведерникова С.В.' }, 
          { title: 'Social Studies', cabinet: 35, teacher: 'Свинкина И.А.' }, 
          { title: 'English', cabinet: 35, teacher: 'Долгополова Э.В.' }, 
          { title: 'IT', cabinet: 40, teacher: 'Завъялова А.Н.' }], 
        Sa: [
          { title: 'Literature', cabinet: 35, teacher: 'Лукашевская Я.Н.'}, 
          { title: 'PE', cabinet: "Спортзал", teacher: 'Зиненко Т.В.' }, 
          { title: 'Chemistry', cabinet: 31, teacher: 'Шелякина Т.В.' }], 
      }],

      timelesson: [{
        Mo: { start: '8:10', end: '8:50'},
        Tu: { start: '8:55', end: '9:35'},
        We: { start: '9:50', end: '10:30'},
        Th: { start: '10:45', end: '11:25'},
        Fr: { start: '11:40', end: '12:20'},
        Sa: { start: '12:25', end: '13:05'},
      }]
    }
  }
}
</script>


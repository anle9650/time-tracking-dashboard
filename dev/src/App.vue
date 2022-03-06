<template>
  <section class="container my-auto">
      <div class="row">
        <!-- Left Column -->
        <div class="col-lg-3 mb-4">
          <ProfileCard @select-timeframe="(timeframe) => this.timeframe = timeframe" />
        </div>

        <!-- Right Column -->
        <div class="col-lg">
          <!-- Row 1 -->
          <div class="row">
            <div class="col-lg mb-4">
              <ActivityCard activity="work" :activityData="activities[0]" :timeframe="timeframe" />
            </div>
            <div class="col-lg mb-4">
              <ActivityCard activity="play" :activityData="activities[1]" :timeframe="timeframe" />
            </div>
            <div class="col-lg mb-4">
              <ActivityCard activity="study" :activityData="activities[2]" :timeframe="timeframe" />
            </div>
          </div>

          <!-- Row 2 -->
          <div class="row">
            <div class="col-lg mb-4">
              <ActivityCard activity="exercise" :activityData="activities[3]" :timeframe="timeframe" />
            </div>
            <div class="col-lg mb-4">
              <ActivityCard activity="social" :activityData="activities[4]" :timeframe="timeframe" />
            </div>
            <div class="col-lg mb-4">
              <ActivityCard activity="self-care" :activityData="activities[5]" :timeframe="timeframe" />
            </div>
          </div>
        </div>
      </div>
    </section>

    <div class="attribution">
      Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. Coded by <a href="#">Andy Le</a>.
    </div>
</template>

<script>
import ProfileCard from './components/ProfileCard.vue'
import ActivityCard from './components/ActivityCard.vue'
import activityData from './assets/data.json';

export default {
  name: 'App',
  components: {
    ProfileCard,
    ActivityCard
  },
  data() {
    return {
      activities: activityData,
      timeframe: 'daily'
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Rubik:wght@300;400;500&display=swap');

html,
body {
  height: 100%;
  font-family: 'Rubik', sans-serif;
  background-color: hsl(226, 43%, 10%);
}

.card {
  border: 0;
  min-height: 100%;
  border-radius: 15px;
  background-color: hsl(235, 46%, 20%);
}
.card .card-title {
  color: white;
  font-weight: 400;
  font-size: 18px;
}
.card a {
  color: hsl(235, 45%, 61%);
  text-decoration: None;
}
.card a:hover,
.card a.active {
  color: white;
}

.attribution {
  color: white;
  font-size: 11px;
  text-align: center;
}
.attribution a {
  color: hsl(228, 45%, 44%);
}
</style>

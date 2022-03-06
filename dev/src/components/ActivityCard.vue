<template>
  <div :class="['card', `card-${activity}`]">
    <div class="card content-card pt-2 pb-3 mt-5">
      <div class="card-body">
        <div class="d-flex justify-content-between align-items-center">
          <h5 class="card-title">
            {{ activity.charAt(0).toUpperCase() + activity.slice(1) }}
          </h5>
          <img
            class="ellipses-img"
            src="../assets/images/icon-ellipsis.svg"
            alt="ellipses"
          />
        </div>
        <div
          class="
            d-flex
            justify-content-between
            align-items-center
            flex-lg-column
            align-items-lg-start
          "
        >
          <div class="card-current">
            {{ activityData.timeframes[timeframe].current }}hrs
          </div>
          <div class="card-previous">
            {{
              timeframe === "daily"
                ? "Yesterday"
                : timeframe === "weekly"
                ? "Last Week"
                : timeframe === "monthly"
                ? "Last Month"
                : ""
            }}
            - {{ activityData.timeframes[timeframe].previous }}hrs
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ActivityCard",
  props: {
    activity: String,
    activityData: Object,
    timeframe: String,
  },
};
</script>

<style scoped>
.card-work {
  background-image: url("../assets/images/icon-work.svg");
  background-color: hsl(15, 100%, 70%);
}
.card-play {
  background-image: url("../assets/images/icon-play.svg");
  background-color: hsl(195, 74%, 62%);
}
.card-study {
  background-image: url("../assets/images/icon-study.svg");
  background-color: hsl(348, 100%, 68%);
}
.card-exercise {
  background-image: url("../assets/images/icon-exercise.svg");
  background-color: hsl(145, 58%, 55%);
}
.card-social {
  background-image: url("../assets/images/icon-social.svg");
  background-color: hsl(264, 64%, 52%);
}
.card-self-care {
  background-image: url("../assets/images/icon-self-care.svg");
  background-color: hsl(43, 84%, 65%);
}

.card .card-current {
  color: white;
  font-size: 3em;
  font-weight: 300;
}
.card .card-previous {
  color: hsl(235, 45%, 61%);
}

.content-card:hover {
  cursor: pointer;
  background-color: hsl(235, 45%, 40%);
}

img.ellipses-img:hover {
  filter: brightness(0) invert(1);
  cursor: pointer;
}
</style>

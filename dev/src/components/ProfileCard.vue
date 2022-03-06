<template>
  <div class="card">
    <div class="card card-profile p-2">
      <div
        class="
          card-body
          d-flex
          align-items-center
          flex-lg-column
          align-items-lg-start
        "
      >
        <img
          class="w-25 mr-3"
          src="../assets/images/image-jeremy.png"
          alt="jeremy"
        />
        <div>
          <span class="card-text mt-0">Report for</span>
          <h4 class="card-title mb-0">Jeremy Robson</h4>
        </div>
      </div>
    </div>
    <div class="card-body">
      <div class="d-flex flex-lg-column justify-content-between m-2">
        <a
          :class="['mb-lg-3', timeframe === 'daily' ? 'active' : '']"
          href="#"
          @click="selectTimeframe('daily')"
          >Daily</a
        >
         <a
          :class="['mb-lg-3', timeframe === 'weekly' ? 'active' : '']"
          href="#"
          @click="selectTimeframe('weekly')"
          >Weekly</a
        >
         <a
          :class="[timeframe === 'monthly' ? 'active' : '']"
          href="#"
          @click="selectTimeframe('monthly')"
          >Monthly</a
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProfileCard",
  emits: ["select-timeframe"],
  data() {
    return {
      timeframe: "daily",
    };
  },
  methods: {
    selectTimeframe(timeframe) {
      this.timeframe = timeframe;
      this.$emit("select-timeframe", timeframe);
    },
  },
};
</script>

<style scoped>
.card-profile {
  background-color: hsl(246, 80%, 60%);
}
.card-profile img {
  border: solid;
  border-color: white;
  border-radius: 50%;
}
.card-profile .card-title {
  font-weight: 300;
  color: white;
}
.card-profile .card-text {
  color: hsl(236, 100%, 87%);
}

@media only screen and (min-width: 768px) {
  .card-profile img {
    margin-bottom: 2em;
  }
  .card-profile .card-title {
    font-size: 2.5em;
    line-height: 1.2em;
    padding-bottom: 1em;
  }
}

@media only screen and (min-width: 992px) {
  .card-profile img {
    width: 45% !important;
  }
}
</style>
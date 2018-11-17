<template>
  <div class="main">
    <datepicker-tor />
  </div>
</template>

<script>
import datepickerTor from "./components/datepickertor";

export default {
  name: "App",
  components: {
    datepickerTor
  }
};
</script>

<style lang="stylus" scoped>
.main
  width 100%
  margin 80px auto
  display flex
  justify-content center
</style>


<template>
  <div id="app">
    <time-table msg="A timeline of the late bronze age"/>
  </div>
</template>

<script>
import TimeTable from './components/TimeTable.vue'

export default {
  name: 'App',
  components: {
    TimeTable
  }
}
</script>

<style lang="scss">
@import url('./style/global.scss');
</style>

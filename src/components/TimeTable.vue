<template>
  <div class="cdr-container">
    <cdr-text tag="h1" modifier="heading-serif-900">{{ msg }}</cdr-text>

    <cdr-table border>
      <thead>
        <tr>
          <th id="stripedhead1" scope="col">Year (B.C.E.)</th>
          <th id="stripedhead2" scope="col"></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="thing in things" :key="thing.year">
          <td headers="stripedhead1">{{ thing.year }}</td>
          <td headers="stripedhead2">
            <div class="events" v-if="thing.events.length">
              <div class="event" v-for="(stuff, tags, index) in thing.events" :key="index">
                {{ stuff.event }}
              </div>
            </div>
            
          </td>
        </tr>
      </tbody>
    </cdr-table>
  </div>
</template>

<script>
import { CdrTable, CdrText } from '@rei/cedar';
import things from './events';

export default {
  name: 'TimeTable',
  props: {
    msg: String
  },
  components: {
    CdrTable,
    CdrText,
  },
  data() {
    return {
      things
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.event:not(:first-child) {
  margin-top: 0.8rem;
}
</style>

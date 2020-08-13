<template>
  <div>
    <h3 class="text-uppercase my-3">Schedule</h3><h6 class="my-3">
    It's going to be busy that today. You have
    <b>{{events.length}} events</b> today.
  </h6>
    <h1 class="my-3">
      <mdb-row>
        <mdb-col col="3" class="text-center">
          <mdb-icon far icon="sun"/>
        </mdb-col>
        <mdb-col col="9">Sunny</mdb-col>
      </mdb-row>
      <mdb-row>
        <mdb-col col="3" class="text-center">
          <mdb-icon icon="thermometer-three-quarters"/>
        </mdb-col>
        <mdb-col col="9">23°C</mdb-col>
      </mdb-row>
    </h1>
    <p>
      Don't forget your sunglasses. Today will dry and sunny, becoming
      warm in the afternoon with temperatures of between 20 and 25
      degrees.
    </p>
  </div>
</template>
<script>
import {mdbCol, mdbRow, mdbIcon} from "mdbvue";

export default {
  name: 'DayOverView',
  components: {

    mdbRow,
    mdbCol,
    mdbIcon
  },
  props: {
    events: {}
  }
}
</script>

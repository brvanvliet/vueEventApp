<template>
  <div id="eventsContainer">
    <h2 class="text-uppercase my-3">Today:</h2>
    <Event
        v-for="(event, index) in events"
        :index="index" :time="event.time" :title="event.title"
        :location="event.location" :description="event.description"
        :key="index"
        @delete="handleDelete"
    />
    <mdb-row>
      <mdb-col xl="3" md="6" class="mx-auto text-center">
        <mdb-btn color="info" @click.native="handleModal">Add Event</mdb-btn>
      </mdb-col>
    </mdb-row>
  </div>
</template>
<script>
import Event from "@/components/Event"
import {mdbBtn, mdbCol, mdbRow} from "mdbvue";

export default {
  name: 'EventsOverview',
  components: {Event,
    mdbBtn,
    mdbCol,
    mdbRow},
  props: {
    events: {},
  },
  methods: {
    handleDelete(eventIndex) {
      this.$emit("delete", eventIndex)
    },
    handleModal() {
      this.$emit("modal")
    }
  }
}
</script>

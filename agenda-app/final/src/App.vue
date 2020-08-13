<template>
  <mdb-container>
    <mdb-row>
      <mdb-col col="9">
        <EventsOverview :events="events" @delete="handleDelete" @modal="modal=true"/>
      </mdb-col>

      <mdb-col col="3">
        <DayOverView :events="events"/>
      </mdb-col>
    </mdb-row>

    <mdb-modal v-if="modal" @close="modal = false">
      <NewEventModal @addEbent="addEvent" @input="handleInput"/>
    </mdb-modal>
  </mdb-container>
</template>

<script>
import {mdbCol, mdbContainer, mdbModal, mdbRow} from "mdbvue";
import EventsOverview from "./components/EventsOverview";
import DayOverView from "./components/DayOverView";
import NewEventModal from "./components/NewEventModal";

export default {
  name: "App",
  components: {
    NewEventModal,
    DayOverView,
    EventsOverview,
    mdbContainer,
    mdbRow,
    mdbCol,
    mdbModal
  },
  data() {
    return {
      events: [
        {
          time: "10:00",
          title: "Breakfast with Simon",
          location: "Lounge Caffe",
          description: "Discuss Q3 targets"
        },
        {
          time: "10:30",
          title: "Daily Standup Meeting (recurring)",
          location: "Warsaw Spire Office"
        },
        {
          time: "11:00",
          title: "Call with HRs"
        },
        {
          time: "12:00",
          title: "Lunch with Timmoty",
          location: "Canteen",
          description: "Project evalutation "
        }
      ],
      modal: false,
      newValues: []
    };
  },
  methods: {
    handleDelete(eventIndex) {
      this.events.splice(eventIndex, 1);
    },
    handleInput(val, type) {
      console.log(val)
      this.newValues[type] = val;
    },
    addEvent() {
      this.events.push({
        time: this.newValues["time"],
        title: this.newValues["title"],
        location: this.newValues["location"],
        description: this.newValues["description"]
      });
    }
  }
};
</script>


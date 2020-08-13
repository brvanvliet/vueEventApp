<template>
  <div>
    <mdb-modal-header>
      <mdb-modal-title tag="h4" class="w-100 text-center font-weight-bold">Add new event</mdb-modal-title>
    </mdb-modal-header>
    <mdb-modal-body>
      <form class="mx-3 grey-text">
        <mdb-input
            name="time"
            label="Time"
            icon="clock"
            placeholder="12:30"
            type="text"
            @input="handleInput"
        />
        <mdb-input
            name="title"
            label="Title"
            icon="edit"
            placeholder="Briefing"
            type="text"
            @input="handleInput"
        />
        <mdb-input
            name="location"
            label="Location (optional)"
            icon="map"
            type="text"
            @input="handleInput"
        />
        <mdb-textarea
            name="description"
            label="Description (optional)"
            icon="sticky-note"
            @input="handleInput"
        />
      </form>
    </mdb-modal-body>
    <mdb-modal-footer class="justify-content-center">
      <mdb-btn color="info" @click.native="addEvent">Add</mdb-btn>
    </mdb-modal-footer>
  </div>
</template>
<script>
import {
  mdbModalHeader,
  mdbModalTitle,
  mdbModalBody,
  mdbModalFooter,
  mdbInput,
  mdbTextarea, mdbBtn,
} from "mdbvue";

export default {
  name: 'NewEventModal',
  components: {
    mdbModalHeader,
    mdbModalTitle,
    mdbModalBody,
    mdbModalFooter,
    mdbInput,
    mdbTextarea,
    mdbBtn
  },
  props: {
    addEvent: {}
  },
  methods:{
    handleInput(val, type) {
      this.$emit("input", val, type);
    },
  }
}
</script>

<template>
  <div>
    <AddNote @new-note="addNote" />

  </div>
</template>

<script>
import AddNote from './components/AddNote.vue';

export default {
  components: {
    AddNote,
  },
  data() {
    return {
      notes: []
    };
  },
  methods : {
    addNote(newNote) {
      this.notes.push({ ...newNote, id: Date.now()});
    },
  }
};

</script>
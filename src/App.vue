<template>
  <div>
    <Home/>
    <AddNote @new-note="addNote" />

  </div>
</template>

<script>
import Home from './components/Home.vue';
import AddNote from './components/AddNote.vue';

export default {
  components: {
    AddNote,
    Home
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
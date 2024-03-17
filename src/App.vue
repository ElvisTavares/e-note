<template>
  <div>
    <Home/>
    <AddNote @new-note="addNote" />
    <ListNote :notes="notes" @delete-note="deleteNote"/>
  </div>
</template>

<script>
import Home from './components/Home.vue';
import AddNote from './components/AddNote.vue';
import ListNote from './components/ListNote.vue';

export default {
  components: {
    AddNote,
    Home,
    ListNote
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
    deleteNote(id) {
      this.notes = this.notes.filter(note => note.id !== id);
    }
  }
};

</script>
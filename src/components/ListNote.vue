<template>
    <div>
        <div v-for="note in notes" :key="note.id">
            <h3>  {{ note.title }}</h3>
            <p> {{ note.content }}</p>
            <button @click="deleteNote(note.id)">Excluir</button>
        </div>
    </div>
</template>

<script>
export default {
    props : ['notes'],
    methods: {
        deleteNote(id) {
            this.$emit('delete-note', id);
        }
    }
}
</script>
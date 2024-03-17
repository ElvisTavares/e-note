<template>
    <form action="" @submit.prevent="addNote">
        <input type="text" v-model="title" placeholder="Titulo">
        <textarea v-model="content"  placeholder="Conteúdo" cols="30" rows="10"></textarea>
        <button type="submit">Adicionar nota</button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                title: '',
                content: '',
            };
        },
        methods : {
            addNote() {
                const note = {
                    title: this.title,
                    content: this.content,
                };

                this.$emit('new-note', note);
                this.title = '';
                this.content = '';
            }
        }
    };
</script>
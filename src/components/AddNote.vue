<template>
    <div class="container">
        <div class="background">
            <div class="content">
                <form action="" @submit.prevent="addNote">
                <input type="text" v-model="title" placeholder="Titulo">
                <textarea v-model="content"  placeholder="Conteúdo" cols="30" rows="10"></textarea>
                <button type="submit">Adicionar nota</button>
                </form>
            </div>
        </div>
    </div>
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

<style scoped>
    form input,
    form textarea,
    form button{
        display: block;
    }
    .container {
        display:flex;
        justify-content: center;
        align-items: center;
        border-radius: 5px;
       

    }
    .background {
        background-color: #f2f2f2;
        border-radius: 5px;
    }

    .content {
        display: inline-block;
        padding: 20px;
    }

    input[type=text], textarea {
        width: 100%;
        padding: 12px 20px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid #ccc;
        border-radius: 4px;
        box-sizing: border-box;
    }

    button[type=submit] {
        width: 100%;
        background-color: #6959CD;
        color: white;
        padding: 14px 20px;
        margin: 8px 0;
        border: none;
        border-radius: 4px;
        cursor: pointer;
    }
</style>


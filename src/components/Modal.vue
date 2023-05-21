<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{dark: theme === 'dark', light: theme === 'light'}">
            <h1>{{header}}</h1>
            <p>{{text}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['header', 'text', 'theme'],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }
}
</script>

<style>
.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}

.modal {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 400px;
    height: 200px;
    margin: 100px auto;
    background: white;
    border-radius: 15px;
}

.modal.dark {
    background: black;
    color: white;
}

.modal.light {
    background: white;
    color: black;
}

</style>
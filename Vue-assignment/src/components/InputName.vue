<template>
    <div
        style="
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        "
    >
        <div>
            <input v-model="name" placeholder="Enter your name" />
            <button @click="submitForm" :disabled="!name">Submit</button>
            <p v-if="showMessage && isNaN(name)">Hej {{ name }}, välkommen</p>
            <p v-else-if="showMessage">Varning, du måste skriva in ett namn</p>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                name: '',
                showMessage: false
            }
        },
        methods: {
            submitForm() {
                this.showMessage = true
            }
        }
    }
</script>

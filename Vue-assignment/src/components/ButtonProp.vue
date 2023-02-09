<template>
    <div
        style="
            position: absolute;
            top: 4rem;
            left: 50%;
            transform: translate(-50%, 0);
        "
    >
        <button @click="increment" class="increment-btn">{{ count }}</button>
    </div>
</template>

<script>
    export default {
        props: ['start'],
        data() {
            return {
                count: this.start
            }
        },
        methods: {
            increment() {
                this.count++
            }
        }
    }
</script>

<style>
    .increment-btn {
        padding: 1rem 2rem;
        font-size: 1.5rem;
    }
</style>

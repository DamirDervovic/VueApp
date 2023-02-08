<template>
    <div class="flex-container">
        <button @click="fetchCharacters" class="knappen">
            Fetch Characters
        </button>
        <div
            v-for="character in characters"
            :key="character.id"
            class="main-div"
        >
            <div>
                <h2>{{ character.name }}</h2>
                <p>Status: {{ character.status }}</p>
                <p>Species: {{ character.species }}</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                characters: []
            }
        },
        methods: {
            async fetchCharacters() {
                const response = await fetch(
                    'https://rickandmortyapi.com/api/character?limit=10'
                )
                const data = await response.json()
                this.characters = data.results
            }
        }
    }
</script>

<style>
    .flex-container {
        display: flex;
        margin-top: 10rem;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
    }
    .knappen {
        justify-content: center;
        margin-bottom: 1rem;
    }
    .main-div {
        height: auto;
        padding: 0.5rem;
        width: 10rem;
        border: 1px solid black;
        align-self: center;
        margin: 0.5rem;
    }
</style>

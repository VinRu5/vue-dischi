<template>
    <header>
        <div class="logo-container">
            <img src="../assets/spotify-logo.png" alt="logo Spotify">
        </div>

        <div>

            <label for="genre">Filtra</label>
            <select v-model="selectGenre" @change="$emit('choice', selectGenre)" id="genre">
                <option v-for="genre in optionGenre" :key="genre.id" 
                    :value="genre.value">
                    {{ genre.text }}
                </option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            selectGenre: 'all',
            optionGenre: [
                {
                    id: 0,
                    text: 'All',
                    value: 'all'
                },
                {
                    id: 1,
                    text: 'Rock',
                    value: 'Rock'
                },
                {
                    id: 2,
                    text: 'Pop',
                    value: 'Pop'
                },
                {
                    id: 3,
                    text: 'Jazz',
                    value: 'Jazz'
                },
                {
                    id: 4,
                    text: 'Metal',
                    value: 'Metal'
                }
            ],
        }
    },
    methods: {
    }
}
</script>

<style lang="scss" scoped>
@import '../style/_colors.scss';

    header {
        background-color: $primary-color;
        padding: 12px 18px;
        display: flex;
        justify-content: space-between;

        .logo-container {
            width: 60px;

            img {
                width: 100%;
            }
        }
    }
</style>
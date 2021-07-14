<template>
    <header>
        <div class="logo-container">
            <img src="../assets/spotify-logo.png" alt="logo Spotify">
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style lang="scss" scoped>
@import '../style/_colors.scss';

    header {
        background-color: $primary-color;
        padding: 12px 18px;

        .logo-container {
            width: 60px;

            img {
                width: 100%;
            }
        }
    }
</style>
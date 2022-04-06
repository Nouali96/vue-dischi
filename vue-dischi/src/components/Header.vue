<template>
    <header class="d-flex justify-content-between ps-3 pe-3"> 
        <div>
            <img src="../assets/spotify-logo.png" alt="Spotify">
        </div>
        <select v-model="selectedGenre" name="" id="" @change="$emit('selectedGenreE', selectedGenre)">
            <option value="">Seleziona un genere</option>
            <option v-for="(genre, index) in genresList" :value="genre" :key="index">{{genre}}</option>
        </select>
    </header>
</template>

<script>
export default {
    name:"Header",
    props:{
        'genresList':Array
        },
    data() {
        return {
            selectedGenre: ''
        }
    }
}
</script>

<style lang="scss" scoped>
    header {
        height: 70px;
        background-color: #2e3a46;
        line-height: 70px;
        img {
            width: 50px;
        }
    }

</style>
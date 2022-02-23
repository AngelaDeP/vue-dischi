<template>
    <div class="song-card" >
        <div class="card-content">
            <img :src="song.poster">
            <h1>{{song.title}}</h1>
            <span>{{song.author}}</span>
            <span>{{song.year}}</span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'MySongCard',
    props: {
        song: Object
    }
}
</script>

<style>
@import "../assets/style/song-card-style.scss";
</style>
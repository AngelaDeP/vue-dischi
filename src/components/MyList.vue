<template>
    <div class="bg-color">
        <div class="container">
            <MySongCard v-for="(song, index) in songList.response" :key="index" :song="song" />
        </div>      
    </div>
</template>

<script>

const axios = require('axios');
import MySongCard from '../components/MySongCard.vue';

export default {
  name: 'MyList',
  
  data() {
    return {
        songList: []
    }
  },
  components: {
      MySongCard
  },
  methods: {
        getSongList() {

            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response) => {
                this.songList = response.data;
                console.log(response);
            })
            .catch(function (error) {
                console.log(error);
            })
            .then(function () {
            });

        }
    },
    created() {
        this.getSongList();
    }
}
</script>

<style lang="scss">
@import "../assets/style/list-content-style.scss";
</style>
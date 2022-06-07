<template>
    <section>
        <div class="container">
            <div class="row">
                <div class="album" v-for="album in albums" :key="album">
                    <div class="album-img" :style="{ backgroundImage: 'url(' + album.poster + ')' }"></div>
                    <h5>{{album.title}}</h5>
                    <p>{{album.author}}</p>
                    <p>{{album.year}}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

import axios from 'axios';

export default {

    name: 'MainComponent',

    data() {
        return {
            albums: [],
        }
    },

    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            // handle success
            this.albums = response.data.response;
        })
        .catch(function (error) {
            // handle error
            console.log(error);
        });
    }
    
}

</script>

<style lang="scss" scoped>
    
    section {
        background-color: var(--secondary-color);
    }

    .container {
        display: flex;
        align-items: center;
        height: calc(100vh - 60px);
        overflow: auto;
    }

    .row {
        justify-content: center;
        gap: 30px;
    }

    .album {
        display: flex;
        flex-direction: column;
        text-align: center;
        max-width: 15%;
        background-color: var(--primary-color);
        padding: 14px;

        &-img {
            height: 180px;
            background-position: center;
            background-size: cover;
        }

        h5 {
            margin: 14px 0;
            color: white;
            text-transform: uppercase;
        }

        p {
            color: grey;
            margin: 0;
        }
        
    }



</style>
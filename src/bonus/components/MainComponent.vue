<template>
    <main>
        <div class="cards_wrapper container">
            <ul class="cards_list" v-if="ready === true">
                <li class="list_item card" v-for="(album, i) in filterAlbums" :key="`${i}alb`">
                    <CardComponent :card="album" />
                </li>
            </ul>
            <ul v-else>
                <li>
                    <LoaderComponent />
                </li>
            </ul>
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import CardComponent from '../../components/CardComponent.vue';
import LoaderComponent from './LoaderComponent.vue';

export default {
    name: "MainComponent",
    props: {
        genre: {
            type: String,
            default: ''
        },
        author: {
            type: String,
            default: ''
        }
    },
    data() {
        return {
            albums: [],
            ready: false,
        };
    },
    computed: {
        filterAlbums() {
            return this.albums.filter((el) => {
                const genre = el.genre.toLowerCase()
                const author = el.author.toLowerCase()
                const findGenre = this.genre.toLowerCase()
                const findAuthor = this.author.toLowerCase()

                if (genre.includes(findGenre) && author.includes(findAuthor)) {
                    console.log(genre, author)
                    return true
                }

                return false
            })
        }
    },
    mounted() {
        axios
            .get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((res) => {
                // console.log(res.data.response)
                this.albums = res.data.response;
                this.ready = true;
            });
    },
    components: { CardComponent, LoaderComponent }
}
</script>
<style lang="scss" scoped>
@import '../../style/index.scss';

main {
    height: 100vh;
    color: $ds-accent_ligth;
    background-color: $ds-bg;

    display: flex;
    align-items: center;
    justify-content: center;

    .cards_list {
        gap: 1rem;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;

        .card {
            text-align: center;
            padding: 1rem 1rem 2rem;
            background-color: $ds-accent;
            flex-basis: calc((100% / 5) - 1rem);
        }
    }
}
</style>
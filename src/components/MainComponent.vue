<template>
    <main>
        <div class="cards_wrapper container">
            <ul class="cards_list">
                <li class="list_item card" v-for="(album, i) in albums" :key="`${i}alb`">
                    <CardComponent :card="album" />
                </li>
            </ul>
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import CardComponent from './CardComponent.vue';

export default {
    name: "MainComponent",
    data() {
        return {
            albums: []
        };
    },
    mounted() {
        axios
            .get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((res) => {
                // console.log(res.data.response)
                this.albums = res.data.response;
            });
    },
    components: { CardComponent }
}
</script>
<style lang="scss" scoped>
@import '../style/index.scss';

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
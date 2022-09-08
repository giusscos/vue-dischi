<template>
    <header>
        <div class="header_wrapper">
            <img src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fpnggrid.com%2Fwp-content%2Fuploads%2F2021%2F05%2FSpotify-PNG-Logo-1536x1534.png&f=1&nofb=1"
                alt="logo-spotify" />
            <select class="genre" @change="$emit('search', genres[1])">
                <option v-for="(genre,i) in genres" 
                        :key="`${i}gen`"
                        :value="genre"
                >{{ genre }}
                </option>
            </select>
        </div>
    </header>
</template>
<script>
const genres = ['Rock', 'Pop', 'Jazz']

export default {
    name: 'HeaderComponent',
    data() {
        return{
            genres
        }
    }
}
</script>
<style lang="scss" scoped>
@import '../style/index.scss';

header {
    padding: 0.5rem 1rem;
    background-color: $ds-accent;

    .header_wrapper {
        display: flex;

        img {
            width: 50px;
            height: 50px;
            aspect-ratio: 1/1;
        }

        .genre {
            margin-left: auto;
            padding: 0.5rem 1rem;
            outline: 1px solid $ds-bg;

            cursor: pointer;
            font-weight: bold;
            color: $ds-accent_ligth;
            border: 2px solid $ds-accent_ligth;

            transition: 300ms ease-in-out;

            &:hover {
                color: $ds-accent_dark;
                background-color: $ds-accent_ligth;
            }
        }
    }
}
</style>
<template>
    <header>
        <div class="header_wrapper">
            <img src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fpnggrid.com%2Fwp-content%2Fuploads%2F2021%2F05%2FSpotify-PNG-Logo-1536x1534.png&f=1&nofb=1"
                alt="logo-spotify" />
            <select class="select genre" v-model="selectedGenre" @change="$emit('searchGen', selectedGenre)">
                <option disabled value="">Please select one genre</option>
                <option value="">All</option>
                <option>Metal</option>
                <option>Rock</option>
                <option>Pop</option>
                <option>Jazz</option>
            </select>
            <select class="select author" v-model="selectedAuthor" @change="$emit('searchAut', selectedAuthor)">
                <option disabled value="">Please select one author</option>
                <option value="">All</option>
                <option>Michael Jacjson</option>
                <option>Queen</option>
                <option>Metallica</option>
                <option>Bon jovi</option>
            </select>
        </div>
    </header>
</template>
<script>

export default {
    name: 'HeaderComponent',
    data() {
        return {
            selectedGenre: '',
            selectedAuthor: ''
        }
    }
}
</script>
<style lang="scss" scoped>
@import '../../style/index.scss';

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

        .select {

            margin-right: 1rem;
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
            
            &.genre {
                margin-left: auto;
            }
        }
    }
}
</style>
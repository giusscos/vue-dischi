<template>
    <header>
        <div class="header_wrapper">
            <img src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fpnggrid.com%2Fwp-content%2Fuploads%2F2021%2F05%2FSpotify-PNG-Logo-1536x1534.png&f=1&nofb=1"
                alt="logo-spotify" />
            <select class="genre" v-model="selectedGen" @change="$emit('searchGen', selectedGen)">
                <option disabled value="">Please select one</option>
                <option value="">All</option>
                <option>Metal</option>
                <option>Rock</option>
                <option>Pop</option>
                <option>Jazz</option>
            </select>
        </div>
    </header>
</template>
<script>

export default {
    name: 'HeaderComponent',
    data() {
        return {
            selectedGen: ''
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
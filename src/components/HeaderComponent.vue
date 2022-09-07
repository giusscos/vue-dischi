<template>
    <header>    
        <div class="logo_wrapper">
            <img height="50px" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fpnggrid.com%2Fwp-content%2Fuploads%2F2021%2F05%2FSpotify-PNG-Logo-1536x1534.png&f=1&nofb=1" alt="logo-spotify"/>
        </div>
    </header>   
</template>
<script>
export default {
    name: 'HeaderComponent',
}
</script>
<style lang="scss" scoped>
    @import '../style/index.scss';

    header{
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        padding: 0.5rem 1rem;
        background-color: $ds-accent;
    }
</style>
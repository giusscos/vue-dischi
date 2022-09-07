<template>
    <div class="loader">
        <h1>
            Carico...
        </h1>
    </div>
</template>
<script>
export default {
    name: 'LoaderComponent'
}
</script>
<style lang="scss" scoped>
@import '../../style/index.scss';

.loader{
    position: absolute;
    top:50%;
    left: 50%;
    transform: translate(-50%);

    h1{
        color: $ds-accent_ligth;
    }
}
</style>
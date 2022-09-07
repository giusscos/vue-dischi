<template>
    <div>
        <div class="card_img-wrapper">
            <img :src="card.poster" :alt="card.title" />
        </div>
        <h3 class="card_title">
            {{ card.title }}
        </h3>
        <p class="card_desc">
            {{ card.author }} <br>
            {{ card.year }}
        </p>
    </div>
</template>
<script>
export default {
    name: 'CardComponent',
    props: {
        card: Object,
    }
}
</script>
<style lang="scss" scoped>
@import '../style/index.scss';

.card_title {
    padding: 1rem 0;
    font-weight: bold;
}

.card_desc {
    color: $ds-accent_dark;
}
</style>    
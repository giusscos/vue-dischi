<template>
    <div class="loader_wrapper">
        <div class="loader">
            <span class="square_center"> Loading... </span>
            <span class="square top"></span>
            <span class="square bottom"></span>
        </div>
    </div>
</template>
<script>
export default {
    name: 'LoaderComponent'
}
</script>
<style lang="scss" scoped>
@import '../../style/index.scss';

.loader_wrapper{
    position: absolute;
    top:50%;
    left: 50%;
    transform: translate(-50%);

    .loader{
        position: relative;
        width: 100px;
        aspect-ratio: 3/2;

        .square{
            position: absolute;
            top: 0;
            left: 0;
            transform: translate(-50%, -50%);
            
            width: 2rem;
            height: 2rem;
            border-radius: 50%;
            aspect-ratio: 1/1;
            background-color: $ds-accent_ligth;

            &.top{
                top: 0;
                left: 100%;
                animation: loaderDotTop infinite 2000ms linear;
            }
            &.bottom{
                top: 100%;
                left: 0;
                animation: loaderDotBot infinite 2000ms linear;
            }
        }
        .square_center{
            display: flex;
            align-items: center;
            justify-content: center;
            
            color: $ds-bg;
            padding: 2rem;
            font-weight: bold;
            border-radius: 0.5rem;
            background-color: $ds-accent_ligth;
        }
    }
}
</style>
<template>
    <div class="wrapper">
        <slot></slot>
    </div>
</template>

<script >

export default {
name: 'cut-corners-wrapper',
}
</script>

<style lang="scss" scoped>
//#region Variables
$background-color: white;
$border-color: white;
$border-width: 0.2em;
$edge-size: 1em;
//#endregion Variables

//#region Cut Corners
.wrapper {
    border: white solid 0.3rem;
    padding: 0.2vh 0.1vw;
    border: 0px;
    position: relative;
    display: inline-grid;
    place-content: center;

    clip-path: polygon(
                    $edge-size 0%,
                    100% 0,
                    100% calc(100% - $edge-size),
                    calc(100% - $edge-size) 100%,
                    0 100%,
                    0% $edge-size
                );
}

.wrapper::before {
    content: "";
    position: absolute;
    inset: 0;
    background: $border-color;
    z-index: -2;
}
.wrapper::after {
    content: "";
    position: absolute;
    inset: 0;
    background: $page__bg;
    z-index: -1;
    clip-path: polygon(
                    // top left 1
                    $border-width calc($edge-size + $border-width * 0.5),
                    // top left 2
                    calc($edge-size + $border-width * 0.5) $border-width,
                    // top right
                    calc(100% - $border-width) $border-width,
                    //bottom right - 1
                    calc(100% - $border-width)
                    calc(100% - calc($edge-size + $border-width * 0.5)),
                    // bottom right - 2
                    calc(100% - calc($edge-size + $border-width * 0.5))
                    calc(100% - $border-width),
                    // bottom left
                    calc($border-width) calc(100% - $border-width)
                );
}
//#endregion Cut Corners

</style>
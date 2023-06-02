<template>
    <li class="li-default">
        <span class="li-default__icon">&#10065;</span>
        <slot></slot>
    </li>
</template>

<script>

export default {
name: 'my-li',
}
</script>

<style lang="scss" scoped>
.li-default {

    &__icon {
        padding:0 1rem 0 2rem;
    }
}

</style>
<template>
  <div class="big-number-font-size color-main font-weight-bold">{{ number }}</div>
</template>

<script>
export default {
    name: 'big-number',
    props: {
        number: [String, Number]
    }
}
</script>

<style lang="scss">
    .big-number-font-size {
        font-size: 288px;
    }
</style>
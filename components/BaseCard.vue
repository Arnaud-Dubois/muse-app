<template>
    <div class="w-1/6 text-center mx-8 pt-20 pb-10">
        <h5 class="text-6xl font-bold">{{ step }}.</h5>
        <h4 class="text-3xl mb-6">{{ title }}</h4>
        <p>
            <slot></slot>
            {{ desc }}
        </p>
    </div>
</template>

<script>
export default {
    name: 'base-card',
    props: {
        step: String,
        title: String,
        desc: String
    }
}
</script>

<style>

</style>
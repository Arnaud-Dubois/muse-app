<template>
    <div class="frame-card w-full md:w-1/6 text-center md-0 md:mx-8 px-8 pt-10 pb-20">
        <h5 class="frame-card-step text-6xl font-bold">{{ step }}.</h5>
        <h4 class="font-bold text-3xl mb-6">{{ title }}</h4>
        <p class="text-2xl leading-tight">
            <slot></slot>
        </p>
    </div>
</template>

<script>
export default {
    name: 'frame-card',
    props: {
        step: String,
        title: String
    }
}
</script>

<style lang="scss">
    .frame-card {
        /* border: 15px solid #8610FC; */
        border: 12px solid #5800D9;
        border-radius: 2px;

        p {
           color: #c7c3ff;
        }
    }
    .frame-card-step {
        font-size: 6rem;
    }
</style>
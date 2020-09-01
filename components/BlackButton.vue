<template>
    <button
        :class="[border ? 'bg-transparent border border-main' : 'bg-black']"
        class="base-button text-white font-bold text-2xl uppercase px-6 py-2 rounded-full w-full md:w-auto"
    >
        {{ title }}
        <slot></slot>
    </button>  
</template>

<script>
export default {
    name: 'black-button',
    props: {
        title: String,
        border: Boolean
    }
}
</script>
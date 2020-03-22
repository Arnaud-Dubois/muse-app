<template>
    <button
        :class="[border ? 'bg-transparent border border-main' : 'bg-main']"
        class="text-white font-bold text-2xl uppercase px-10 py-2 rounded-full w-full md:w-auto"
    >
        {{ title }}
        <slot></slot>
    </button>  
</template>

<script>
export default {
    name: 'base-button',
    props: {
        title: String,
        border: Boolean
    }
}
</script>
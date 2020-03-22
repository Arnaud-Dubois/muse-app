<template>
    <section
        :style="{ backgroundImage: image ? `url(${image})` : 'none', backgroundSize: 'contain' }"
        :class="{ 'bg-main-gradient' : color }" class="container-fullwidth text-white"
    >
        <div
            :style="{ backgroundColor: image ? `rgba(0,0,0,0.9)` : null }"
            
        >
            <slot></slot>
        </div>
    </section>
</template>

<script>
export default {
    name: 'base-section',
    props: {
        color: Boolean,
        image: String
    }
}
</script>

<style>

</style>
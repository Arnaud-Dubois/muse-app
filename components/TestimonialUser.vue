<template>
    <div>
        <div
            :class="{'border-4 border-purple-500 transform scale-150' : user.isFocus}"
            class="w-24 h-24 mx-4 bg-white rounded-full overflow-hidden border-2 border-white transition-all duration-500"
        >
            <img :src="user.src" :alt="user.alt">
        </div>
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: 'testimonial-user',
    props: {
        user: Object
    }
}
</script>
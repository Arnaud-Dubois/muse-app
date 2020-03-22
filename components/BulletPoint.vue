<template>
    <div class="flex items-center p-4">
        <div class="w-1/4">
            <div class="w-6 h-6 rounded-full bg-white"></div>
        </div>
        <div class="w-screen text-2xl text-left">
            <slot></slot>
        </div>
        
    </div>
</template>

<script>
export default {
    name: 'bullet-point'
}
</script>

<style>

</style>
<template>
    <section
        :style="{ backgroundImage: image ? `url(${image})` : null, backgroundSize: image ? 'contain' : 'initial' }"
        :class="{ 'bg-purple-test point-tile' : color }" class="container-fullwidth text-white"
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

<style lang="scss">
    .base-section-title {
        font-size: 6rem;
    }
      @media screen and (max-width: 767px) {
        .base-section-title {
            font-size: 3rem;
        }
    }

    .point-tile {
        position: relative;
        &::after {
            background-image: url('~@/assets/point_tile_texture.png')!important;
            pointer-events: none;
            position: absolute;
            content: "";
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
    }

    .museum-tour {
        position: relative;
        &::after {
            background-image: url('~@/assets/museum_tour.svg')!important;
            background-repeat: no-repeat;
            pointer-events: none;
            position: absolute;
            content: "";
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            object-fit: contain;
            width: 100%;
            height: 100%;
            z-index: -1;
        }
    }

    /* bg-main-gradient */
    .bg-purple-test {
        background-color: #5F19DD;
        /* 541e8a */
    }
</style>
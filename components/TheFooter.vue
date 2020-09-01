<template>
    <footer class="bg-purple-test the-footer py-8">
        <div class="container">

        <!-- Social links -->
        <div class="flex justify-center pt-4 pb-16">
            <ul class="text-2xl text-white">
                <li class="inline px-1">
                    <a target="_blank" href="https://www.facebook.com/"><font-awesome-icon :icon="['fab', 'facebook']"/></a>
                </li>
                <li class="inline px-1">
                    <a target="_blank" href="https://twitter.com/?lang=fr"><font-awesome-icon :icon="['fab', 'twitter']"/></a>
                </li>
                <li class="inline px-1">
                    <a target="_blank" href="https://www.instagram.com/?hl=fr"><font-awesome-icon :icon="['fab', 'instagram']"/></a>
                </li>
            </ul>
        </div>
        <!-- / Social links -->

        <!-- Terms -->
        <div class="flex flex-wrap justify-between">

            <div>
                <TheLogoWord class="block md:inline-block mx-auto"/>
                <ul class="inline-block mt-4 md:mt-0 ml-0 md:ml-6">
                    <li class="inline px-3 md:px-4">
                        <a href="#">Privacy policy</a>
                    </li>
                    <li class="inline px-3 md:px-4">
                        <a href="#">Terms of use</a>
                    </li>
                    <li class="inline px-3 md:px-4">
                        <a href="#">Regulatory informations</a>
                    </li>
                </ul>
            </div>

            <span class="inline-block mx-auto mt-4 md:mt-0">Copyright© - Musa 2020</span>
        </div>
        <!-- / Terms -->

        </div>
    </footer>
</template>

<script>
import TheLogoWord from '~/components/TheLogoWord'
export default {
    name: 'the-footer',
    components: {
        TheLogoWord
    }
}
</script>

<style lang="scss">
    .the-footer {
        a {
            transition: all .2s ease;
            &:hover {
                color: white;
            }
        }
    }

</style>
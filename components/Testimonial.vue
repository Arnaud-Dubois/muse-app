<template>
    <div class="flex flex-wrap justify-center m-0 md:m-20">
        <TestimonialUser
            :key="user.name"
            v-for="user in users"
            :user="user"
        >
            <div class="mt-6 absolute inset-x-0">
                <div v-if="user.isFocus" class="flex justify-center my-4">
                    <StarIcon
                        :key="index"
                        v-for="index in 5"
                        :fill="user.ratings < index ? 'white' : 'yellow'"
                    />
                </div>
            </div>
            <div class="mt-20 absolute inset-x-0">
                <transition name="fade">
                    <div v-if="user.isFocus">
                        <div class="text-2xl">"{{ user.testimonial }}"</div>
                    </div>
                </transition>
            </div>    
        </TestimonialUser>
    </div>
</template>

<script>
import TestimonialUser from './TestimonialUser'
import StarIcon from './icons/StarIcon'

export default {
    name: 'testimonial-container',
    components: {
        TestimonialUser,
        StarIcon
    },
    data() {
        return {
            users: [
                { isFocus: true, src: 'images/persona-man-01.jpg', ratings: 1, alt: 'profile', name: 'John', testimonial: 'It\'as great App to visit museums.'},
                { isFocus: false, src: 'images/persona-man-02.jpg', ratings: 2, alt: 'profile', name: 'Johny', testimonial: 'The ultimate experience of art !'},
                { isFocus: false, src: 'images/persona-woman-01.jpg', ratings: 3, alt: 'profile', name: 'Jane', testimonial: 'MuseAPP is the best app to look for museum guidance !'},
                { isFocus: false, src: 'images/persona-man-03.jpg', ratings: 4, alt: 'profile', name: 'Jack', testimonial: 'I love MuseAPP, Super app !'},
                { isFocus: false, src: 'images/persona-woman-02.jpg', ratings: 5, alt: 'profile', name: 'Jill', testimonial: 'Another one please :)'}
            ]
        }
    },
    mounted() {
        setInterval(() => {
            let show = this.users.find(element => element.isFocus === true)
            let indexNextShow = this.users.indexOf(show) + 1
            if(indexNextShow > 4) {
                indexNextShow = 0
            }
            show.isFocus = false
            this.users[indexNextShow].isFocus = true
        }, 3000);
    }
}
</script>

<style lang="css">
    .fade-enter-active, .fade-leave-active {
        transition: all 0.5s
    }
    .fade-enter, .fade-leave-to {
        opacity: 0;
        transform: translateX(-10px);
    }

</style>
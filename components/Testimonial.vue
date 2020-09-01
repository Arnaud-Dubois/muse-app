<template>
    <div class="flex flex-wrap justify-center m-0 md:m-4">
        <TestimonialUser
            :key="user.name"
            v-for="user in users"
            :user="user"
        >
            <div class="relative inset-x-0">
                <div v-if="user.isFocus" class="my-8">
                    <div class="text-2xl text-bold">{{ user.name }}</div>
                </div>
                <div v-if="user.isFocus" class="flex justify-center my-4">
                    <StarIcon
                        :key="index"
                        v-for="index in 5"
                        :fill="user.ratings < index ? 'white' : 'yellow'"
                    />
                </div>
            </div>
            <div class="relative inset-x-0">
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
                { isFocus: true, src: 'images/persona-man-01.jpg', ratings: 4, alt: 'profile', name: 'Mark', testimonial: 'It\'as great App to visit museums.'},
                { isFocus: false, src: 'images/persona-man-02.jpg', ratings: 5, alt: 'profile', name: 'Gabriel', testimonial: 'The ultimate experience of art !'},
                { isFocus: false, src: 'images/persona-woman-01.jpg', ratings: 5, alt: 'profile', name: 'Jane', testimonial: 'MUSA is the best app to look for museum guidance !'},
                { isFocus: false, src: 'images/persona-man-03.jpg', ratings: 4, alt: 'profile', name: 'Alex', testimonial: 'I love MUSA, Super app !'},
                { isFocus: false, src: 'images/persona-woman-02.jpg', ratings: 5, alt: 'profile', name: 'Jill', testimonial: 'Met a lot of people there. Great app :)'}
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
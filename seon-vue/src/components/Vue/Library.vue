<template>
    <ul class="library" ref="lib">
        <Books />
    </ul>
</template>

<script>
import Books from './Books.vue';

export default {
    components: {
        Books
    },
    methods: {
        load() {
            if(this.$route.path == '/') {
                this.$refs.lib.childNodes[2].classList.remove('active')
                this.$refs.lib.childNodes[1].classList.add('active')
            }
            if(this.$route.path == '/About') {
                this.$refs.lib.childNodes[1].classList.remove('active')
                this.$refs.lib.childNodes[2].classList.add('active')
            }
        }
    },
    mounted() {
        window.addEventListener('load', this.load);
        this.load();
    },
    unmounted() {
        window.addEventListener('load', this.load);
    }
}
</script>
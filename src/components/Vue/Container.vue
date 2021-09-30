<template>
    <div class="container">
        <Header @v-update="update" />
        <Main />
    </div>
</template>

<script>
import Header from './Header.vue';
import Main from './Main.vue';

export default {
    components: {
        Header,
        Main
    },
    methods: {
        update() {
            this.$emit('v-update');
        }
    }
}
</script>
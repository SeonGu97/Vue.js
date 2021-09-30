<template>
    <header>
        <Menu @v-update="update" />
        <Logo />
    </header>
</template>

<script>
import Menu from './Menu.vue';
import Logo from './Logo.vue';

export default {
    components: {
        Menu,
        Logo
    },
    methods: {
        update() {
            this.$emit('v-update');
        }
    }
}
</script>
<template>
    <div class="menu">
        <a href="#" @click="update"><i class="fas fa-bars"></i></a>
    </div>
</template>

<script>
export default {
    methods: {
        update() {
            this.$emit('v-update');
        }
    },
}
</script>
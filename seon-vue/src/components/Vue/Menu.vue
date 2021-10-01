<template>
    <div class="menu" @click="update">
        <i class="fas fa-bars"></i>
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
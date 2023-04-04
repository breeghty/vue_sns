<template>
    <div>
        <postSns></postSns>
        <postSns></postSns>
        <postSns></postSns>
    </div>
</template>

<script>
import postSns from './Post.vue';

export default {
    name: 'ContainerBox',
    components: {
        postSns: postSns,
    },
}
</script>

<style>

</style>
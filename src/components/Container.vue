<template>
    <div>
        <postSns v-for="(post, i) in dataList" :key="post" :dataList = "dataList[i]"></postSns>
        <!-- <postSns :dataList = "dataList[1]"></postSns>
        <postSns :dataList = "dataList[2]"></postSns> -->
    </div>
</template>

<script>
import postSns from './Post.vue';

export default {
    name: 'ContainerBox',
    props: {
        dataList: Array,
    },
    components: {
        postSns: postSns,
    },
}
</script>

<style>

</style>
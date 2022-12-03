<template>
    <!-- v-if solves the issue when no video is selected -->
    <div v-if="selectedVideo">
        Video Detail
        {{ selectedVideo.snippet.title }}
    </div>
</template>

<script>
export default {
    name: 'VideoDetails',
    props: {
        'selectedVideo': Object
    },
    computed: {
        thumbnailUrl() {
            return this.video.snippet.thumbnails.default.url;
        },
        videoTitle() {
            return this.video.snippet.title;
        }
    },
    methods: {
    },
};
</script>

<style>
</style>
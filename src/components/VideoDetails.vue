<template>
    <!-- v-if solves the issue when no video is selected -->
    <div class="row my-2" v-if="selectedVideo">
        <div class="ratio ratio-16x9">
            <iframe v-bind:src="embeddedURL" v-bind:title="videoTitle" frameborder="1" allowfullscreen></iframe>
        </div>
        <div class="details">
            <h4>{{ selectedVideo.snippet.title }}</h4>
            <p>{{ selectedVideo.snippet.description }}</p>
        </div>
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
        },
        embeddedURL() {
            // const videoId=this.video.id.videoId;
            const { videoId } = this.selectedVideo.id;
            // return "https://www.youtube.com/embed/" + videoId;
            return `https://www.youtube.com/embed/${videoId}`;
        }
    },
    methods: {
    },
};
</script>

<style scoped>
.details {
    margin-top: 10px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
}
</style>
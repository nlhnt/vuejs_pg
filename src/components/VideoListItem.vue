<template>
    <li class="list-group-item media d-flex">
        <img class="mr-3" v-bind:src="thumbnailUrl"/>
        <div class="media-body">
            {{ video.snippet.title }}
        </div>
    </li>
</template>

<script>
export default {
    name: 'VideoListItem',
    props: {
        'video': Object
    },
    // props: ['video'],
    computed: {
        thumbnailUrl() {
            return this.video.snippet.thumbnails.default.url;
        }
    }
};
</script>

<style>
li {
    cursor: pointer;
}

li:hover {
    background-color: #eee;
}
</style>
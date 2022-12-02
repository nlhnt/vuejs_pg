<template>
    <li class="list-group-item">
        VideoListItem: {{ video.snippet.title }}
    </li>
</template>

<script>
export default {
    name: 'VideoListItem',
    props: {
        'video': Object
    }
    // props: ['video']
};
</script>
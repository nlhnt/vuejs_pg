<template>
    <li>
        <p>VideoListItem: {{ video.snippet.title }}</p>
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
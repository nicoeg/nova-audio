<template>
    <p>
        <audio
            v-if="field.previewUrl"
            class="block w-full"
            controls
            controlslist="nodownload"
            :src="src"
            :autoplay="autoplay"
            :preload="preload"
        />
        <span v-else>&mdash;</span>
    </p>
</template>

<script>
export default {
    props: ['viaResource', 'viaResourceId', 'resourceName', 'field'],

    data() {
        return {
            src: this.field.previewUrl,
        }
    },

    computed: {
        preload() {
            return this.field.preload || 'none'
        },
        autoplay() {
            return this.field.autoplay || false
        }
    }
}
</script>

<template>
    <div id="app" :style="{height:appHeight}">
        <router-view></router-view>
    </div>
</template>

<script>
    export default {
        computed: {
            appHeight() {
                if (document.getElementById('title'))
                    return (window.innerHeight - document.getElementById('title').offsetHeight) + 'px';
                else
                    return '100%';
            }
        },
        data() {
            return {}
        },
        created: function () {
            if (process.platform !== 'darwin') {
                document.getElementById('title').remove();
            }
        },
        mounted() {
        }
    }
</script>

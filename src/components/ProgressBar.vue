<template>
        <div class="empty">
            <div class="progress" :style="{width: progress}">
                <p>{{ quotesNumber }}/ {{ quotesMax }}</p>
            </div>
        </div>
</template>

<script>
    export default {
        name: "ProgressBar",
        props: {
            quotesNumber: Number,
            quotesMax: Number
        },
        computed: {
            progress() {
                return ((this.quotesNumber / this.quotesMax) * 100) + '%';
            }
        }
    }
</script>

<style scoped>
    .empty {
        border-radius: 5px;
        background-color: lightgray;
    }

    .progress {
        background-color: #46b8da;
        width: 0;
    }

    p {
        color: #fff;
        margin-left: 45%;
    }
</style>
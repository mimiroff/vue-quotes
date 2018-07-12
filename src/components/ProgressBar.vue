<template>
        <div class="empty">
            <div class="progress">
                <p>1/10</p>
            </div>
        </div>
</template>

<script>
    export default {
        name: "ProgressBar"
    }
</script>

<style scoped>
    .empty {
        border-radius: 5px;
        background-color: lightgray;
    }

    .progress {
        background-color: #46b8da;
        width: 10%;
    }

    p {
        color: #fff;
        margin-left: 45%;
    }
</style>
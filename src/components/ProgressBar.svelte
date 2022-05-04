<script>
    export let progress = 20;
</script>

<div class="container">
    <div class="progress-container">
        <div class="progress-bar" style="width: {progress}%">
            <span class="sr-only">{progress}%</span>
        </div>
    </div>
</div>

<style>
    .progress-container {
        margin: 20px 0;
        border: solid black;
    }
    .progress-bar {
        height: 30px;
        background-color: rgb(77, 199, 55);
    }
</style>

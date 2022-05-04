<script>
    import ProgressBar from "./ProgressBar.svelte";
    const totalSeconds = 2;
    let secondsLeft = totalSeconds;
    let isRunning = false;
    $: progress = ((totalSeconds - secondsLeft) / totalSeconds) * 100;
    function startTimer() {
        isRunning = true;
        const timer = setInterval(() => {
            secondsLeft -= 1;
            if (secondsLeft == 0) {
                clearInterval(timer);
                isRunning = false;
                secondsLeft = totalSeconds;
            }
        }, 1000);
    }
    $: console.log(secondsLeft);
</script>

<div class="container">
    <h2 class="col-4-md col-12-sm" style="margin: 0;">
        Seconds left:{secondsLeft}
    </h2>
</div>
<ProgressBar {progress} />
<div class="container d-flex justify-content-center">
    <button class="start" disabled={isRunning} on:click={startTimer}>
        Start
    </button>
</div>

<style>
    .start {
        background-color: rgb(154, 73, 73);
        max-width: 578px;
        margin: 10px 0;
    }
    .start[disabled] {
        background-color: black;
        cursor: not-allowed;
    }
</style>

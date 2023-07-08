<script>
    let audio;
    export let width = "100px";

    const CLOSED = "https://slaska.xyz/closed.png";
    const OPEN = "https://slaska.xyz/open.png";
    let src = CLOSED;

    function pop() {
        src = OPEN;
        audio.currentTime = 0;
        audio.play();
    }

    function unpop() {
        src = CLOSED;
    }
</script>

<audio src="https://slaska.xyz/pop.ogg" bind:this={audio}></audio>

<img
    {src}
    alt="pop cat"
    {width}
    on:pointerdown={pop}
    on:pointerout={unpop}
    on:pointerup={unpop}
    draggable="false"
>

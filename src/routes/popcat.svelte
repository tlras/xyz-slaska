<script>
    let audio;

    const CLOSED = "https://slaska.xyz/closed.png";
    const OPEN = "https://slaska.xyz/open.png";
    let cat_src = CLOSED;

    function pop() {
        cat_src = OPEN;
        audio.currentTime = 0;
        audio.play();
    }

    function unpop() {
        cat_src = CLOSED;
    }
</script>

<audio src="https://slaska.xyz/pop.ogg" bind:this={audio}></audio>
<img
    src={cat_src}
    alt="pop cat"
    width="100px"
    on:pointerdown={pop}
    on:pointerup={unpop}
>
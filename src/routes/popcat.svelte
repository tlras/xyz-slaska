<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();

    let audio;
    export let width = "100vw";

    const CLOSED = "https://slaska.xyz/closed.png";
    const OPEN = "https://slaska.xyz/open.png";
    let cat_src = CLOSED;

    function pop() {
        dispatch("pop");
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
    {width}
    on:pointerdown={pop}
    on:pointerout={unpop}
    on:pointerup={unpop}
    draggable="false"
>
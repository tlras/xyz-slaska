<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();

    let audio;
    export let width = "100vw";

    const CLOSED = "/closed.png";
    const OPEN = "/open.png";
    let src = CLOSED;

    function pop() {
        dispatch("pop");
        src = OPEN;
        audio.currentTime = 0;
        audio.play();
    }

    function unpop() {
        src = CLOSED;
    }
</script>

<audio src="/pop.ogg" bind:this={audio}></audio>

<img
    {src}
    alt="pop cat"
    {width}
    on:pointerdown={pop}
    on:pointerout={unpop}
    on:pointerup={unpop}
    on:taphold|preventDefault|stopPropagation={false}
    on:contextmenu|preventDefault|stopPropagation={false}
    draggable="false"
>
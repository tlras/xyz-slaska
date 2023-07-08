<svelte:head>
    <meta property="og:description" content="several popcats" />
	<meta property="description" content="several popcats" />
</svelte:head>

<script>
    import Popcat from "./popcat.svelte";
    import Unsel from "./unsel.svelte";
    let count = 0;
</script>

<Unsel>
    {#each {length: 4} as _}
        <Popcat on:pop={() => count++} />
    {/each}
</Unsel>
<p>Pops: {count.toLocaleString()}</p>
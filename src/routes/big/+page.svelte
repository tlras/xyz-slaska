<svelte:head>
    <meta property="og:description" content="a big popcat" />
	<meta property="description" content="a big popcat" />
</svelte:head>

<script>
    import Popcat from "../popcat.svelte";
    import Unsel from "../unsel.svelte";
    let count = 0;
</script>

<Unsel>
    <Popcat width="400vw" on:pop={() => count++} />
</Unsel>
<p>Pops: {count.toLocaleString()}</p>
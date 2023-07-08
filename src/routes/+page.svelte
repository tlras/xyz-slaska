<script>
    import Popcat from "./popcat.svelte";
</script>

<div id="unsel">
    <Popcat />
    <Popcat />
    <Popcat />
    <Popcat />
</div>

<style>
    div {
        -ms-user-select: none;
        -moz-user-select: none;
        -webkit-user-select: none;
        user-select: none;
    }
</style>
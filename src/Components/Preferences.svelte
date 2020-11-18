<script>
    import Filter from './Filter.svelte';
</script>

<div>
    <Filter filterName={"Kategori"} />
	<Filter filterName={"Sted"} />
    <button>Filtrer</button>
</div>

<style>
    div {
        margin-right: 75px;
    }
    button {
        height: 75%;
    }
</style>
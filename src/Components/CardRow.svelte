<script>
    import Card from './Card.svelte';
    export let studyCodes;
    for (let i=0; i<studyCodes.length; i++) {
        console.log(studyCodes[i]);
    }
</script>

<div class="container">
    {#each studyCodes as code}
        <Card studyCode={code} />
    {/each}
</div>

<style>
    @media screen and (max-width: 850px) {
        .container {
            flex-direction: column;
        }
    }
    .container {
        display: flex;
        flex-direction: row;
    }
</style>
<script>
    export let data;
</script>

<style>
    div {
        font-size: 1rem;
    }
    ul {
        padding-left: 1.2em;
    }
</style>

<div>
    <h1>{data.header}</h1>
    <div>
        <ul>
            {#each data.points as point}
                <li>{point}</li>
            {/each}
        </ul>
    </div>
</div>
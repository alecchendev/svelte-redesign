<script>
    import Article from './Article.svelte';

    export let data;
    const tech = [];
    const other = [];
    data.forEach(article => {
        if (article.category === "tech") {
            tech.push(article);
        } else {
            other.push(article);
        }
    });
</script>

<style>
    .categoryWrapper {
        display: flex;
    }
    .category {
        width: 50%;
    }
</style>

<div>
    <h1>Writing</h1>
    <div class="categoryWrapper">
        <div class="category">
            <h2>Tech</h2>
            {#each tech as article}
                <Article data={article} />
            {/each}
        </div>
        <div class="category">
            <h2>Other</h2>
            {#each other as article}
                <Article data={article} />
            {/each}
        </div>
    </div>
</div>
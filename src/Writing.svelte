<script>
    export let data;
</script>

<style>
    .writing {
        width: 100%;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }
    .article {
        width: 32%;
        margin-right: 1%;
    }
    .imageContainer {
        width: 100%;
        height: 200px;
    }
    img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        border: 1px solid black;
    }
    h2 {
        margin-top: 10px;
    }
    @media screen and (max-width: 810px) {
        .writing {
            flex-direction: column;
        }
        .article {
            width: 100%;
            margin: 0;
        }
        .imageContainer {
            width: 100%;
            height: auto;
        }
        h2 {
            margin-left: 0;
            margin-top: 10px;
            margin-bottom: 25px;
        }
    }
</style>

<div>
    <h1>Featured Writing</h1>
    <p>To read the rest of my pieces, visit my <a href="https://alecchendev.medium.com" target="_blank">Medium</a>.</p>
    <div class="writing">
        {#each data as article}
            <div class="article">
                <div class="imageContainer">
                    <img alt={"Article image"} src={"images/" + article.image} />
                </div>
                <h2><a href={article.link} target="_blank">{article.title}</a></h2>
            </div>
        {/each}
    </div>
</div>
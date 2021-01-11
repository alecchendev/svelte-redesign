<script>
    export let projects = [];
</script>

<style>
    img {
        width: 350px;
        height: auto;
    }
    .project {
        display: flex;
    }
    .projectInfo {
        margin-left: 10px;
    }
    .projectTitle {
        margin: 0;
    }
</style>

<div>
    <h1>Projects</h1>
    {#each projects as project}
        <div class="project">
            <img alt={"project image"} src={"images/" + project.image}/>
            <div class="projectInfo">
                <h2 class="projectTitle">{project.title}</h2>
                <h3 class="projectStack">{project.stack.join(' ')}</h3>
                <p class="projectDescription">{project.description}</p>
            </div>
        </div>
    {/each}
</div>
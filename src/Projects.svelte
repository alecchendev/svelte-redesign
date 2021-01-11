<script>
    export let projects = [];
</script>

<style>
    
    .project {
        display: flex;
        margin-bottom: 10px;
    }
    .projectImage {
        width: 400px;
        height: 100%;
    }
    .projectInfo {
        margin-left: 10px;
    }
    .projectTitle {
        margin: 0;

        font-size: 2rem;
    }
    .projectStack {
        margin: 0;
        margin-top: 5px;

        font-size: 1.25rem;
        font-weight: normal;
    }
    .projectDescription {
        margin: 0;
        margin-top: 10px;

        font-size: 1.1rem;
    }

    @media screen and (max-width: 1450px) {
        .project {
            flex-direction: column;
        }

        .projectImage {
            width: 100%;
            height: auto;
        }
        
        .projectInfo {
            margin-left: 0;
            margin-top: 10px;
            margin-bottom: 25px;
        }
    }

    @media screen and (max-width: 1160px) {
        .project {
            flex-direction: row;
            margin-bottom: 10px;
        }

        .projectImage {
            width: 400px;
            height: 100%;
        }
        
        .projectInfo {
            margin-left: 10px;
            margin-top: 0px;
            margin-bottom: 20px;
        }
    }

    @media screen and (max-width: 850px) {
        .project {
            flex-direction: column;
        }

        .projectImage {
            width: 100%;
            height: auto;
        }
        
        .projectInfo {
            margin-left: 0;
            margin-top: 10px;
            margin-bottom: 25px;
        }
    }
</style>

<div>
    <h1>Projects</h1>
    {#each projects as project}
        <div class="project">
            <img class="projectImage" alt={"project image"} src={"images/" + project.image}/>
            <div class="projectInfo">
                <h2 class="projectTitle">{project.title}</h2>
                <h3 class="projectStack">{project.stack.join(' ')}</h3>
                <p class="projectDescription">{project.description}</p>
            </div>
        </div>
    {/each}
</div>
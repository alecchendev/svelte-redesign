<script lang="ts" context="module">
	export type ProjectShape = {
        image: string,
        title: string,
        stack: ReadonlyArray<string>,
        description: string,
    };
    export let project;
</script>

<div>
    <img alt={"project image"} src={project.image}/>
    <h2>{project.title}</h2>
    <h3>{project.stack.join(' ')}</h3>
    <p>{project.description}</p>
</div>
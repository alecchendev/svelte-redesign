<script lang="ts">
    export let data;
</script>

<style>
    .iconContainer {
        display: flex;
        justify-content: space-between;

        width: 150px;
        margin: auto;
        margin-top: 100px;
        text-align: center;
    }
    .iconContainer:hover .socialIcon {
        opacity: 0.5;
    }
    .socialIcon {
        font-size: 1.75rem;
        background-image: none;
        opacity: 1;
        transition: 0.15s;
    }
    .iconContainer:hover .socialIcon:hover {
        opacity: 1;
        background-image: linear-gradient(180deg,transparent 90%, var(--link-color) 0);
    }
</style>

<div class="iconContainer">
    <a class="socialIcon" href={data.email} target="_blank"><i class="fas fa-envelope"></i></a>
    <a class="socialIcon" href={data.github} target="_blank"><i class="fab fa-github"></i></a>
    <a class="socialIcon" href={data.medium} target="_blank"><i class="fab fa-medium"></i></a>
    <a class="socialIcon" href={data.linkedin} target="_blank"><i class="fab fa-linkedin"></i></a>
</div>
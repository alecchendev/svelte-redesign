<script>
    export let navigate;
</script>

<style>
    .header {
        margin: auto;

        display: flex;
        justify-content: space-between;

        font-size: 1.1rem;
    }
    .right {
        width: 40%;
        
        display: flex;
        justify-content: space-between;
    }
    .navLink:hover {
        text-decoration: underline;
        cursor: pointer;
    }
</style>

<div class="header">
    <div class="left"><div class="navLink" on:click={navigate("summary")}>Alec Chen</div></div>
    <div class="right">
        <div class="navLink" on:click={navigate("summary")}>Home/About</div>
        <div class="navLink" on:click={navigate("projects")}>Projects</div>
        <div class="navLink" on:click={navigate("writing")}>Writing</div>
    </div>
</div>
<script>

    export let ingameName;
    export let name;
    export let role;

    const roles = ['top', 'jgl', 'mid', 'adc', 'sup'];

</script>

<div class="player-view">
    <div>{name}</div>
    <div>"{ingameName}"</div>
    {#if roles.includes(role)}
        <img alt={role} src="{"/assets/fbs/icons/" + role + ".png"}">
    {:else}
        <div>{role}</div>
    {/if}
    <a href="{"https://www.leagueofgraphs.com/summoner/euw/" + ingameName}" target="_blank">Profil</a>
</div>

<style>


    .player-view * {
        text-align: center;
    }

    .player-view {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
</style>
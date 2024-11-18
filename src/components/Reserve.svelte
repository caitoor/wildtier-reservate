<script>
    import Hyena from "./Hyena.svelte";
    import Gnu from "./Gnu.svelte";

    export let width;
    export let height;
    export let plants;
    export let gnus;
    export let hyenas;
    export let id;
    let hyenaArray = [];
    let gnuArray = [];

    for (let i = 0; i < hyenas; i++) {
        hyenaArray.push(i);
    }

    for (let i = 0; i < gnus; i++) {
        gnuArray.push(i);
    }

    function mapColor(value, start = [243, 245, 159], end = [54, 99, 12]) {
        value = value / 100;
        const r = start[0] + (end[0] - start[0]) * value;
        const g = start[1] + (end[1] - start[1]) * value;
        const b = start[2] + (end[2] - start[2]) * value;
        return `rgb(${r}, ${g}, ${b})`;
    }
</script>

<div
    class="reserve"
    style={`width: ${width}px; height: ${height}px; background-color: ${mapColor(plants)}`}
>
    {#each gnuArray as _, i}
        <Gnu />
    {/each}

    {#each hyenaArray as _, i}
    <Hyena />
{/each}
    <div class="reserve-label">
        <h2>Reservat {id + 1}</h2>
        <p>{plants}% bewachsen, {Math.round((width * height) / 1000)}km²</p>
    </div>
    <div class="count">{gnus + hyenas}</div>
</div>

<style>
    .reserve {
        overflow: hidden;
        border: 7px solid #633903;
        border-radius: 8px;
        width: 200px;
        height: 200px;
        position: relative;
        transition: all 0.3s;
    }

    .reserve:hover {
        cursor: pointer;
        transform: scale(1.1);
    }

    .reserve-label {
        position: absolute;
        bottom: 0;
        width: 100%;
        height: 45px;
        background-color: rgba(255, 255, 255, 0.9);
        padding: 5px;
        border-top: 1px solid #3d2504;
    }

    h2 {
        margin: 0;
        font-size: 1em;
    }

    p {
        margin: 0;
        font-size: 0.8em;
    }

    .count {
        position: absolute;
        font-size: 0.8rem;
        top: 0.5em;
        right: 0.5em;
        color: white;
        padding: 2px;
        border-radius: 50%;
        border: 2px solid white;
        height: 20px;
        width: 20px;
        display: flex;
        justify-content: center;
        align-items: center;
  
        background-color: black;
    }
</style>

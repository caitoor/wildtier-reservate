<script>
    const gender = Math.random() > 0.5 ? "male" : "female";

    function randomPercentage() {
        return `${Math.random() * 100}%`;
    }
</script>

<div
    class="hyena {gender}"
    style={`top: ${randomPercentage()}; left: ${randomPercentage()};`}
></div>

<style>
    .hyena {
        width: 30px;
        height: 30px;
        border-radius: 50%;
        background-size: contain;
        background-repeat: no-repeat;
        background-position: center;
        position: absolute;
        background-image: url("hyena.png");
        box-shadow: 0 0 5px black;
    }

    .female {
        background-color: pink;
    }
    .male {
        background-color: cornflowerblue;
    }
</style>

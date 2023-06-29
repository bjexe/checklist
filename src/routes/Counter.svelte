<script>
    export let goal;
    export let description;
    let count = 0;
    function increase() {
        count = count + 1;
    }
    function decrease(){
        count = count > 0 ? count - 1 : 0;
    }
</script>

<div>
    <h2>{description}</h2>
    <h3>{count}/{goal}</h3>
    <button on:click={increase}>+</button>
    <button on:click={decrease}>-</button>
</div>
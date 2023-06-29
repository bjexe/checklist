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

<div class="border flex flex-col items-center">
    <h2 class="text-2xl">{description}</h2>
    <h3 class="text-2xl">{count}/{goal}</h3>
    <span>
        <button class="text-3xl" on:click={increase}>+</button>
        <button class="text-3xl" on:click={decrease}>-</button>
    </span>
</div>
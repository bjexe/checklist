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

<div class="flex flex-col justify-center items-center mt-[2%]">
    <div class="flex flex-col items-center rounded-3xl lg:w-[20%] bg-[#F1F2EE] gap-y-[15px]">
        <h2 class="text-2xl mt-[5px]">{description}</h2>
        <span class="flex gap-x-10 justify-center items-center">
            <h3 class="text-2xl">{count}/{goal}</h3>
            {#if count === goal}
                <p class="text-2xl">✔️</p>
            {/if}
        </span>
        <span>
            <button class="text-3xl" on:click={increase}>+</button>
            <button class="text-3xl" on:click={decrease}>-</button>
        </span>
    </div>
</div>
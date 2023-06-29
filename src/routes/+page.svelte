<script>
    import Item from './Item.svelte';
    let checklistItems = [
        {
            description: "Leetcode problems",
            goal: 4
        },
        {
            description: "Job apps",
            goal: 10
        },
        {
            description: "Learn something new",
            goal: 1
        },
        {
            description: "Exercise",
            goal: 1
        }
    ];
</script>

<h1 class="text-4xl font-bold underline text-center mt-[2%]">
    Checklist
</h1>

{#each checklistItems as item (item)}
    <Item description={item.description} goal={item.goal}/>
{/each}

<style lang="postcss">
    :global(html) {
        background-color: theme(colors.blue.500);
    }
</style>
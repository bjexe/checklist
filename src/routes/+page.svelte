<script>
    import Item from './Item.svelte';
    let checklistItems = [
        {
            description: "Leetcode problems",
            goal: 3
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
    let addNewItem = false;
    let newItemDescription = "";
    let newItemGoal = 0;
</script>

<h1 class="text-4xl font-bold underline text-center mt-[2%]">
    Daily Checklist
</h1>

{#if !addNewItem}
    <div class="flex justify-center">
        <button class="text-3xl rounded-xl bg-[#F1F2EE] p-4 mt-10" on:click={() => addNewItem = true}>Add a checklist item</button>
    </div>
{/if}

{#if addNewItem}
    <div class="flex justify-center gap-x-4 mt-10 text-3xl">
        <label>
            Description:
            <input class="rounded-xl p-4" type="text" bind:value={newItemDescription} />
        </label>
        <label>
            Goal:
            <input class="rounded-xl p-4" type="number" bind:value={newItemGoal}/>
        </label>
        <button class="rounded-xl bg-[#F1F2EE] w-[10%]" on:click={() => {
            addNewItem = false;
            checklistItems[checklistItems.length] = {
                description: newItemDescription,
                goal: newItemGoal
            }
        }}>Submit</button>
        <button class="rounded-xl bg-[#F1F2EE] w-[10%]" on:click={() => {
            addNewItem = false;
            newItemDescription = "";
            newItemGoal = 0;
        }}>Cancel</button>
    </div>
{/if}

{#each checklistItems as item (item)}
    <Item description={item.description} goal={item.goal}/>
{/each}

<style lang="postcss">
    :global(html) {
        background-color: theme(colors.blue.500);
    }
</style>
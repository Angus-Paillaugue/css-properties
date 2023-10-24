<script>
    let noItems = "3";
    let gap = "10";
    let gridTemplateRows = `repeat(1, 50px)`;
    let gridTemplateColumns = "repeat(3, 1fr)";
</script>


<svelte:head>
    <title>Grid - CSS properties</title>
</svelte:head>


<div class="w-full h-full min-h-[calc(100vh-1rem)] my-2 max-w-screen-md mx-auto border rounded-lg border-neutral-200 p-4 flex flex-col">
    <div class="grid grid-cols-1 md:grid-cols-3 gap-2">
        <div class="flex flex-col">
            <p>Nombre d'éléments : <input type="number" bind:value={noItems} class="inline-block input w-14"></p>
            <input type="range" name="Nombre d'éléments" bind:value={noItems} step="1" min="1" max="50">
        </div>

        <div class="flex flex-col">
            <p>gap : <input type="number" bind:value={gap} class="inline-block input w-14"> px</p>
            <input type="range" name="gap" bind:value={gap} step="1" min="0" max="50">
        </div>
        
        <div class="flex flex-col">
            <p>grid-template-rows</p>
            <input type="text" bind:value={gridTemplateRows} class="w-full input">
        </div>
        
        <div class="flex flex-col">
            <p>grid-template-columns</p>
            <input type="text" bind:value={gridTemplateColumns} class="w-full input">
        </div>
    </div>

    <div class="w-full grow grid p-4 text-white border border-neutral-200 mt-2 rounded-lg overflow-y-auto h-full" style="gap: {gap}px; grid-template-rows: {gridTemplateRows}; grid-template-columns: {gridTemplateColumns};">
        {#each {length : Number(noItems)} as _, i}
            <div class="w-full h-full bg-red-600 flex flex-col items-center justify-center rounded">{i+1}</div>
        {/each}
    </div>
</div>
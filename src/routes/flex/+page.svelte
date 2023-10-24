<script>
    let noItems = "3";
    let gap = "10";
    let flexDir = "row";
    let justContent = "space-between";
    let alignItems = "center";
</script>


<div class="w-full h-full min-h-[calc(100vh-1rem)] my-2 max-w-screen-md mx-auto border rounded-lg border-neutral-200 p-4 flex flex-col">
    <div class="grid grid-cols-1 md:grid-cols-3 gap-2">
        <div class="flex flex-col">
            <p>Nombre d'éléments : <input type="number" bind:value={noItems} class="inline-block input w-14"></p>
            <input type="range" name="Nombre d'éléments" bind:value={noItems} step="1" min="1" max="20">
        </div>
        
        <div class="flex flex-col">
            <p>gap : <input type="number" bind:value={gap} class="inline-block input w-14"> px</p>
            <input type="range" name="gap" bind:value={gap} step="1" min="0" max="50">
        </div>
        
        <div class="flex flex-col">
            <p>flex-direction</p>
            <select bind:value={flexDir} name="flex-direction">
                <option value="row">row</option>
                <option value="column">column</option>
                <option value="row-reverse">row-reverse</option>
                <option value="column-reverse">column-reverse</option>
            </select>
        </div>
        
        <div class="flex flex-col">
            <p>justify-content</p>
            <select bind:value={justContent} name="justify-content">
                <option value="flex-start">flex-start</option>
                <option value="flex-end">flex-end</option>
                <option value="center">center</option>
                <option value="space-between">space-between</option>
                <option value="space-around">space-around</option>
            </select>
        </div>
        
        <div class="flex flex-col">
            <p>align-items</p>
            <select bind:value={alignItems} name="align-items">
                <option value="stretch">stretch</option>
                <option value="flex-start">flex-start</option>
                <option value="flex-end">flex-end</option>
                <option value="center">center</option>
                <option value="baseline">space-between</option>
            </select>
        </div>
    </div>

    <div class="w-full grow flex p-4 text-white border border-neutral-200 mt-2 rounded-lg overflow-auto" style="flex-direction: {flexDir}; gap: {gap}px; justify-content: {justContent}; align-items: {alignItems};">
        {#each {length : Number(noItems)} as _, i}
            <div class="w-14 h-14 bg-red-600 flex flex-col items-center justify-center rounded">{i+1}</div>
        {/each}
    </div>
</div>
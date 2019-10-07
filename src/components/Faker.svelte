<script>
    import {constants} from '../config/config.properties.js';
    import {jsonHeader} from '../config/headers.js';
    let imgData = [], isLoading=false;
    export let defaultVal;
    async function fetchData() {
        isLoading = true;   imgData = [];
        let response = await fetch(constants.apiUrl,{headers : jsonHeader});
        imgData = await response.json();
        isLoading = false;
    }
</script>
<button type="button" on:click={fetchData}>Fetch Data</button>
<div>
    {#if isLoading}
        {defaultVal}
    {/if}
    {#each imgData as img}
        <img alt={img.title} src={img.thumbnailUrl}/>
    {/each}
</div>
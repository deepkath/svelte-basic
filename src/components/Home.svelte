<script>
    import Faker from './Faker.svelte';
    export let inputValue;
    function handleFormSubmit() {
        if(inputValue)
            alert(`form submitted with name ${inputValue}`);
    }
</script>
<div>
    <form on:submit|preventDefault={handleFormSubmit}>
        <input type="text" placeholder="Tell ur name" bind:value={inputValue} />
        <button type="submit">Submit name</button>
    <form>
    <Faker defaultVal="...Loading"/>
</div>
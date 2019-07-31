<script>
    import {createEventDispatcher} from 'svelte';

    // const dispatcher = createEventDispatcher();
    export let answers = [];
    export let selectedAnswer;
</script>
        <div class="form-group">
            <select class="form-select" bind:value={selectedAnswer}>
                <option value="-1">Choose an option</option>
                {#each answers as answer}
                    <option value={answer.id}>{answer.value.split("_").join(" ")}</option>
                 {/each}   
            </select>
        </div> 

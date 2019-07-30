<script>

    /*
        A more reactive solution. Now we need to break this into even more components and figure out a way to propogate data between them
    */

    export let question;
    export let defaultResponseMessage ; 
    export let answers = []
    export let rightAnswer;

    let selectedAnswer;    
    let answerMessageStatus;
    
    // $: defaultResponseMessage = answers[selectedAnswer] !== undefined   ? 
    //                           rightAnswer ==  answers[selectedAnswer].value ? 
    //                           `${question.rightAnswerMessage}` : `${question.wrongAnswerMessage}` : defaultResponseMessage ; 
      
</script>

<div class="card">
  <div class="card-image">
    <img src="{question.url}" class="img-responsive" alt="{question.altText}">
  </div>
  <div class="card-header">
    <div class="card-title h5">{question.title}</div>
    <div class="card-subtitle text-gray">{question.subTitle}</div>
  </div>
  <div class="card-body">
      <p>{question.body}</p>
      <div>
        <div class="form-group">
            <select class="form-select" bind:value={selectedAnswer}>
                <option value="-1">Choose an option</option>
                {#each answers as answer}
                    <option value={answer.id}>{answer.value.split("_").join(" ")}</option>
                 {/each}   
            </select>
        </div>
      </div>
  </div>
  <div class="card-footer">  
   {#if answers[selectedAnswer] === undefined}
        <span>{defaultResponseMessage}</span> 
   {:else if rightAnswer ==  answers[selectedAnswer].value}
        <span>{question.rightAnswerMessage}</span>
   {:else}
        <span>{question.wrongAnswerMessage}</span>
   {/if}
  </div>  
</div>
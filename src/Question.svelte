<script>

    export let question;
    let selectedAnswer;
    let rightAnswer = "peter_parker";
    let answerMessageStatus;
    let responseMessage = "Choose an option";
    
    let answers = [
        {
        id : 0,
        value : "peter_parker"
        },
        {
            id : 1,
            value : "pepper_pots"
        },
        {
            id : 2,
            value : "arun_purushothaman"
        }
    ]

    function _responseMessage(){
        if (answerMessageStatus === undefined){
          return "Choose an answer"
        }else if (answerMessageStatus == true){
        return question.rightAnswerMessage;      
        } else {
        return question.wrongAnswerMessage;
        }
      }    

    function verifyAnswer(){
        
        if(selectedAnswer > -1 ){
          let myAnswer = answers[selectedAnswer].value;          
          if( myAnswer == rightAnswer ){
              answerMessageStatus = true;
          }else{
              answerMessageStatus = false;
          }
          console.log("choose an answer",selectedAnswer,answerMessageStatus);
          responseMessage = _responseMessage();
          console.log(responseMessage);
      } 
    }

    

    $: console.log(answerMessageStatus);
    
    

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
                    <option value={answer.id}>{answer.value}</option>
                 {/each}   
            </select>
        </div>
      </div>
  </div>
  <div class="card-footer">
  <button class="btn btn-primary" on:click={verifyAnswer} >Verify</button>
   <span>{responseMessage}</span> 
  </div>  
</div>
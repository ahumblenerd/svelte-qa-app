<script>


    /*

      This app is strictly not following svelt reactivity pricincples. Need to update it.
    */
    export let question;
    export let rightAnswer;
    export let answers = [ ];
    export let defaultResponseMessage;
    let selectedAnswer;
    let answerMessageStatus;
    
    
    
  
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
          console.log("choose an answer",selectedAnswer,myAnswer,rightAnswer,answerMessageStatus);
          defaultResponseMessage = _responseMessage();
          console.log(defaultResponseMessage);
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
                    <option value={answer.id}>{answer.value.split("_").join(" ")}</option>
                 {/each}   
            </select>
        </div>
      </div>
  </div>
  <div class="card-footer">
  <button class="btn btn-primary" on:click={verifyAnswer} >Verify</button>
   <span>{defaultResponseMessage}</span> 
  </div>  
</div>
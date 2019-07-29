<script>
	import QA from './QA.svelte';
	import Header from './Header.svelte';
	import QuestionWithButton from './QuestionWithButton.svelte';
	import QuestionsReactive from './QuestionsReactive.svelte';

	let links = [{
		url : "http://www.google.com",
		name : "Google"
	}
	];

    
	let defaultResponseMessage =  "🤔 Choose an option";
	let question = {
			url : "https://images.pexels.com/photos/276091/pexels-photo-276091.jpeg?cs=srgb&dl=characters-hero-ironman-276091.jpg&fm=jpg",
			altText : "iron man image",
			title : "Who is the next iron man ?",
			subTitle : "Hint : Current ironman is Tony Stark",
			body : "Your answer is",
			wrongAnswerMessage : "🤣 In your dreams ! Brother",
			rightAnswerMessage : "🤩 Yeay, you guessed it right Bro"
	};
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
	];

	let rightAnswer = "peter_parker";
</script>
<style>
	.cardPadding{
		padding:.5rem;
	}

</style>
<Header links= {links}></Header>
<div class="container grid-lg">
	<div class="columns col-oneline p-centerd">
		<div class="column col-6 cardPadding badge" data-badge="reactive">
			<QuestionsReactive question={question} defaultResponseMessage={defaultResponseMessage} answers={answers} rightAnswer={rightAnswer}></QuestionsReactive>
		</div>
		<div class="column col-6  cardPadding badge" data-badge="non-reactive">
			<QuestionWithButton question={question} rightAnswer={rightAnswer} answers={answers} defaultResponseMessage={defaultResponseMessage}></QuestionWithButton>
		</div>
	</div>
</div>	

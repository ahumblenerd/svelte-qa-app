<script>
	import QA from './QA.svelte';
	import Header from './Header.svelte';
	import Question from './Question.svelte';

	let links = [{
		url : "http://www.google.com",
		name : "Google"
	}
	];

	let question = {
			url : "https://images.pexels.com/photos/276091/pexels-photo-276091.jpeg?cs=srgb&dl=characters-hero-ironman-276091.jpg&fm=jpg",
			altText : "iron man image",
			title : "Who is the next iron man ?",
			subTitle : "Hint : Current ironman is Tony Stark",
			body : "Your answer is",
			wrongAnswerMessage : "🤣 In your dreams ! Brother",
			rightAnswerMessage : "🤩 Yeay, you guessed it right Bro"
	};
</script>
<style>
	.cardPadding{
		padding:2rem;
	}

</style>
<Header links= {links}></Header>
<div class="container grid-lg">
	<div class="row">
	<div class="column col-6 cardPadding p-centered">
		<Question question={question}></Question>
	</div>
	</div>
</div>	

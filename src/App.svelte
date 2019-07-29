<script>
	import QA from './QA.svelte';
	import Header from './Header.svelte';
	import Card from './Card.svelte';

	let links = [{
		url : "http://www.google.com",
		name : "Google.com"
	},
	{
		url : "http://www.google.com",
		name : "Google.com"
	}
	];

	let card = {
			url : "https://wallpapercave.com/wp/wp3324196.jpg",
			altText : "iron man image",
			title : "Who is the next iron man ?",
			subTitle : "Hint : Current ironman is Tony Stark",
			body : "Your answer is",
			footer : "In your dreams ! Brother"
	};
</script>
<style>
	.cardPadding{
		padding:2rem;
	}
</style>
<Header links= {links}></Header>
<div class="cardPadding">
	<Card card={card}></Card>
</div>
<QA/>

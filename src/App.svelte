<script>
	import FeedbackList from './components/FeedbackList.svelte'
	let feedback = [
		{
			id : 1,
			rating : 10,
			text : 'Lorem ipsum 1'
		},
		{
			id : 2,
			rating : 8,
			text : 'Lorem ipsum 2'
		},
		{
			id : 3,
			rating : 7,
			text : 'Lorem ipsum 3'
		},
	]
</script>

<main class='container'>
	<!-- <h1>Hello</h1> -->
	<FeedbackList feedback={feedback}/>
</main>


<script>
	import FeedbackForm from './components/FeedbackForm.svelte'
	import FeedbackList from './components/FeedbackList.svelte'
	import FeedbackStats from './components/FeedbackStats.svelte'
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
	
	$: count = feedback.length
	$: average = feedback.reduce((a , {rating}) => a+rating,0) / feedback.length
	const deleteFeedback = (e) => {
		const itemId = e.detail
		feedback = feedback.filter((item) => item.id != itemId)
		console.log(e.detail)
	}

</script>

<main class='container'>
	<!-- <h1>Hello</h1> -->
	<FeedbackForm/>
	<FeedbackStats {count} {average} /> 
	<!-- <h1>{count}</h1>
	<h1>{average}</h1> -->
	<FeedbackList feedback={feedback} on:delete-feedback= {deleteFeedback}/>
</main>


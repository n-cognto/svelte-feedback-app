<script>
	import FeedbackList from "./components/FeedbackList.svelte";
	// Initial feedback data array
	let feedback = [
  {
    id: 1,
    rating: 10,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
  {
    id: 2,
    rating: 9,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
  {
    id: 3,
    rating: 8,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
]

	// Function to handle deleting feedback items
	const deleteFeedback = (e) => {
  const itemId = e.detail
  feedback = feedback.filter( (item) => item.id != itemId)
}

	// Variables for the feedback form
	let text = '';
	let rating = 10;

	// Function to add new feedback
	const addFeedback = () => {
		const newFeedback = {
			id: Math.max(...feedback.map(f => f.id)) + 1,
			rating: rating,
			text: text
		};
		feedback = [...feedback, newFeedback];
		text = '';
		rating = 10;
	}
</script>

<main class="container">
	<!-- Feedback form to add new feedback -->
	<div class="card">
		<h2>How would you rate your service with us?</h2>
		<div class="input-group">
			<input type="text" placeholder="Write a review" bind:value={text} />
			<button type="button" on:click={addFeedback}>Send</button>
		</div>
		<div class="input-group">
			<label for="rating">Rating:</label>
			<select id="rating" bind:value={rating}>
				<option value="10">10</option>
				<option value="9">9</option>
				<option value="8">8</option>
				<option value="7">7</option>
				<option value="6">6</option>
				<option value="5">5</option>
				<option value="4">4</option>
				<option value="3">3</option>
				<option value="2">2</option>
				<option value="1">1</option>
			</select>
		</div>
	</div>

	<!-- Feedback list component -->
	<FeedbackList {feedback} on:delete-feedback={deleteFeedback} />

</main>


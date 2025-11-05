<script>
  // Import the FeedbackItem component
  import FeedbackItem from './FeedbackItem.svelte'

  // Prop to receive the feedback array from parent component
  export let feedback = []

  // Debug log to see feedback data (can be removed in production)
  console.log(feedback)
</script>

<!-- Loop through each feedback item and render FeedbackItem component -->
{#each feedback as fb (fb.id) }
  <FeedbackItem item={fb} on:delete-feedback />

{/each}
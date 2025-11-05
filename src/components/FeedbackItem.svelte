<script>
    // Import createEventDispatcher to emit custom events
    import {createEventDispatcher} from 'svelte'
    // Import the Card component for styling
    import Card from './Card.svelte'

    // Prop to receive the feedback item data
    export let item

    // Create event dispatcher to communicate with parent component
    const dispatch = createEventDispatcher()

    // Function to handle delete button click
    const handleDelete = (itemId) => {
        dispatch('delete-feedback', itemId)
    }
</script>

<!-- Card component wraps the feedback item content -->
<Card>
    <!-- Display the rating in a circular badge -->
    <div class="num-display">
        {item.rating}
    </div>
    <!-- Delete button positioned in top-right corner -->
    <button class="close" on:click={() => handleDelete(item.id)}>X</button>
    <!-- Display the feedback text -->
    <p class="text-display">
        {item.text}
    </p>
</Card>

<style>
    .num-display {
        position: absolute;
        top:-10px;
        left:-10px;
        width: 50px;
        height: 50px;
        background-color: #ff6a95;
        color:#fff;
        border: 1px #eee solid;
        border-radius: 50%;
        padding: 10px;
        text-align: center;
        font-size: 19px;
    }
    .close {
        position:absolute;
        top: 10px;
        right: 20px;
        cursor: pointer;
        background: none;
        border: none;
    }
</style>
<template>
<div>
	<p>Reaction time: {{ reactionTime }} ms</p>
	<p class="rank">Rank: {{ rank }}</p>
</div>
</template>

<script>
export default {
	name: 'Results',
	props: ['reactionTime'],

	data() {
		return {
			rank: null
		}
	},

	mounted() {
		if (this.reactionTime < 250) { 
			this.rank = "Fast!" 
		} else if (this.reactionTime < 400) { 
			this.rank = "Normal"
		} else {
			this.rank = "Snail pace..."
		}

	}
}
</script>

<style>
	.rank {
		font-size: 1.4em;
		color: #0faf87;
		font-weight: bold;
	}
</style>
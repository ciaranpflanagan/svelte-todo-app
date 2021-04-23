<script lang="ts">
	import Item from './Item.svelte';

	interface TodoItem {
		id: number,
		title: string,
		description: string
	}

	let item: TodoItem = {
		id: 1,
		title: 'Item 1 from data',
		description: 'Item 1 description from data'
	}
</script>

<section class="section">
	<div class="container">
		<div class="columns">
			<div class="column is-half is-offset-one-quarter main-column">
				<Item title="Item 1" />
				<Item title="Item 2" />
				<Item title="Item 3" />
			</div>
		</div>
	</div>
</section>

<style>
.main-column {
	text-align: center;
}
</style>
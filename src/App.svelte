<script lang="ts">
	import Item from './Item.svelte';
	let newTodo: string = '';

	// Test Items
	let items: { id: number, title: string, description: string, completed: boolean }[] = [
		{ id: 1, title: 'Item 1', description: 'Item 1 description from data', completed: false },
		{ id: 2, title: 'Item 2', description: 'Item 2 description from data', completed: false },
		{ id: 3, title: 'Item 3', description: 'Donkeys!', completed: false }
	];

	// Adding new Todo Item
	function addItem () {
		let item = {
			id: items.length + 1,
			title: newTodo,
			description: 'None added yet',
			completed: false
		};

		items.push(item); // Add item to array of items
		items = items; // Update each
	}
</script>

<section class="section">
	<div class="container">
		<div class="columns">
			<div class="column is-half is-offset-one-quarter main-column">
				{#each items as item}
					<Item id={item.id} title={item.title} description={item.description} completed={item.completed} />
				{/each}
			</div>
		</div>
	</div>
</section>
<!-- Add New Todo -->
<section>
	<div class="container add-todo">
		<div class="columns">
			<div class="column is-half is-offset-one-quarter main-column">
				<div class="card">
					<div class="card-content">
						<div class="columns">
							<div class="column is-two-third">
								<input bind:value={ newTodo } placeholder="New Todo Item" type="text" class="input">
							</div>
							<div class="is-one-third">
								<button on:click="{ addItem }" class="button is-primary todo-button">Add Todo</button>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>

<style>
.main-column {
	text-align: center;
}
.add-todo {
	position: fixed;
    bottom: 0;
    width: 100%;
    min-width: 100%;
}
.todo-button {
	margin-top: 12px;
}
</style>
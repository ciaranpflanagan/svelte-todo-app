<script lang="ts">
    import { createEventDispatcher } from "svelte";

    export let id: number;
    export let title: string;
    export let description: string = 'No description given';
    export let completed: boolean = false;

    const dispatch = createEventDispatcher();

    // Completes Item
    function completeItem () {
        completed = true;
    }

    // Deletes/removes an item
    function removeItem (id: number) {
        dispatch('removeItem', { id });
    }
</script>

<div class="card mb-4">
  <div class:completed class="card-content">
    <div class="content mb-4">
        <h1>{ title }</h1>
        <p>
            { description }
        </p>
    </div>
    <div class="columns">
        <div class="column is-one-quarter is-offset-one-quarter">
            <button on:click="{ completeItem }" class="button is-success">
                Complete
            </button>
        </div>
        <div class="column is-one-quarter">
            <button on:click="{ removeItem(id) }" class="button is-danger">
                Remove
            </button>
        </div>
    </div>
  </div>
</div>

<style>
.completed {
    -webkit-filter: grayscale(1);
}
</style>
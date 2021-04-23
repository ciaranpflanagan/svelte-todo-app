<script lang="ts">
    export let title: string;
    export let description: string = 'No description given';
</script>

<div class="card mb-4">
  <div class="card-content">
    <div class="content mb-4">
        <h1>{ title }</h1>
        <p>
            { description }
        </p>
    </div>
    <div class="columns">
        <div class="column is-one-quarter is-offset-one-quarter">
            <button class="button is-success">
                Complete
            </button>
        </div>
        <div class="column is-one-quarter">
            <button class="button is-danger">
                Remove
            </button>
        </div>
    </div>
  </div>
</div>

<style>

</style>
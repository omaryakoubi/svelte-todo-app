<script>
  import { todos } from "../store/stores";
  let todos_value;
  todos.subscribe((value) => (todos_value = value));
</script>

{#each todos_value as todo}
  <div class="card">
    <div class="card-body">{todo}</div>
  </div>
{/each}

<style>
  .card {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 70px;
    width: fit-content;
  }
</style>

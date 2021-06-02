<script>
  import { todos } from "../store/stores";

  let todos_value;
  todos.subscribe((value) => (todos_value = value));

  // const editTodo = (e) => {

  // }

  const deleteTodo = (e) => {
    todos.set(
      todos_value.filter((todo) => {
        console.log(e.target.value);
        return todo.id !== e.target.value;
      })
    );
  };
</script>

{#each todos_value as todo}
  <div class="card">
    <div class="card-body">{todo.task}</div>
    <button on:click={deleteTodo} value={todo.id}>delete</button>
  </div>
{/each}

<style>
  .card {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 70px;
  }
</style>

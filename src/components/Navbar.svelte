<script>
  import { todos } from "../store/stores";
  import { v4 as uuidv4 } from "uuid";

  let todo = "",
    todos_value;

  todos.subscribe((value) => {
    todos_value = value;
  });

  const clearInput = () => (todo = "");

  const setTodo = (e) => {
    e.preventDefault();
    todos.set([...todos_value, { id: uuidv4(), task: todo }]);
    clearInput();
  };
</script>

<nav class="navbar fixed-top navbar-dark bg-dark">
  <div class="container-fluid">
    <h3 id="logo">TODO <span>LIST</span></h3>
    <form class="d-flex">
      <input
        class="form-control me-2"
        placeholder="Add todo"
        bind:value={todo}
      />
      <button class="btn btn-outline-primary" on:click={setTodo}>Add</button>
    </form>
  </div>
</nav>

<style>
  span {
    color: white;
  }

  #logo {
    color: blue;
  }
</style>

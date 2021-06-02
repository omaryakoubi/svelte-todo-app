<script>
  import { todos } from "../store/stores";
  console.log("todos", todos);
  let todo = "",
    todos_value;

  const unsubscribe = todos.subscribe((value) => {
    todos_value = value;
  });

  function getInputValue(e) {
    e.preventDefault();
    todos.set([...todos_value, todo]);
  }
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
      <button class="btn btn-outline-primary" on:click={getInputValue}
        >Add</button
      >
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

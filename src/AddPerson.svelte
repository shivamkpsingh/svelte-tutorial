<script>
  import { createEventDispatcher } from "svelte";
  let dispatch = createEventDispatcher();
  let name;
  let beltColor;
  let age;
  let finghting = false;
  let sneaking = false;
  let runninng = false;
  const addPerson = () => {
    console.log("name, belt color", name, beltColor, age);
    const person = {
      name,
      age,
      id: Math.random(),
    };
    dispatch('addPerson',person)
  };
</script>

<main>
  <h3>add a new person</h3>
  <form action="" on:submit|preventDefault={addPerson}>
    <input type="text" class="hello" placeholder="name" bind:value={name} />
    <input
      type="text"
      class="hello"
      placeholder="belt color"
      bind:value={beltColor}
    />
    <input
      type="number"
      class="hello"
      name=""
      id=""
      placeholder="enter your age"
      bind:value={age}
    />
    <label for="">skills:</label><br />
    <input type="checkbox" bind:checked={finghting} />fighting<br />
    <input type="checkbox" bind:checked={sneaking} />sneaking<br />
    <input type="checkbox" bind:checked={runninng} />running<br />
    <button class="hello">Add People</button>
  </form>
</main>

<style>
  .hello {
    display: flex;
    flex-direction: column;
    margin-top: 6px;
  }
</style>

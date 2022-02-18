<script>
  import Modal from "./Modal.svelte";
  import AddPerson from "./AddPerson.svelte";
  let variable = false;
  let people = [
    { name: "shivam singh", age: 22, id: 1 },
    { name: "shubham singh", age: 20, id: 2 },
    { name: "ashish singh", age: 42, id: 3 },
  ];
  const openModal = () => {
    variable = !variable;
  };
  const handleClick = (id) => {
    //  console.log(person)
    people = people.filter((person) => person.id != id);
  };
  const addPerson = (e) => {
    let person1 = e.detail;
    people = [person1, ...people];
    variable=false
  };
</script>

<Modal showModal={variable} on:click={openModal}>
  <AddPerson on:addPerson={addPerson} />
</Modal>
<main>
  <button on:click={openModal}>open modal</button>
  {#if people.length > 0}
    {#each people as person (person.id)}
      <div>
        <h1>{person.name}</h1>
        <p>{person.age}</p>
        <button
          on:click={() => {
            handleClick(person.id);
          }}>delete</button
        >
      </div>
    {:else}
      <p>hello there are no person</p>
    {/each}
  {/if}
</main>

<style>
</style>

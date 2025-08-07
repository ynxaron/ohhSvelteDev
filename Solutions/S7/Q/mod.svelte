<svelte:head>
    <title>Solutions To Question 7</title>
</svelte:head>

<script>
    const animals = $state(['Tiger', 'Lion', 'Cheetah', 'Leapord']);
    const persons = $state([
      {name: "Satyam", age: 21, editMode: false},
      {name: "Aron", age: 22, editMode: false},
      {name: "Jack", age: 24, editMode: false},
      {name: "Mike", age: 25, editMode: false}
    ]);

    let person = $state({name: '', age: 0});
    const appendToPersons = function() {
      if (!person.hasOwnProperty('name') || !person.hasOwnProperty('age')) {
        console.log("Person has no property 'name' or 'age'");
        return;
      }
      if (persons.map((person) => person.name).includes(person.name)) {
        console.log(`The Provided Name ${person.name} Is Not Unique`);
        return;
      }
      persons.push({name: person.name, age: Number(person.age)});
      console.log(`Property With '${person.name} and '${person.age}' has been added`);
    }
    let choosenPerson = $state('');
    const isMinor = function(person) {
      return (person.age < 18);
    }
</script>

<ul>
    {#each animals as animal}
        <li>{animal}</li>
    {/each}
</ul>

<ol>
    {#each animals as animal, i}
        <li>Name: {animal}, {i}</li>
    {/each}
</ol>

<ul>
    {#each persons
      .filter(
        person =>
        person.name.startsWith(choosenPerson)) as person}
        {#if person.editMode}
            <div>
                <input type="text" placeholder="Enter Name" bind:value={person.name}>
                <input type="text" placeholder="Enter Age" bind:value={person.age}>
                <button onclick={() => person.editMode = false}>Turn Off Edit Mode</button>
            </div>
        {:else}
            <div>
                <li>{person.name} is {person.age} years old</li>
                <button onclick={() => person.editMode = true}>Edit</button>
            </div>
        {/if}
    {/each}
</ul>

<input type="text" placeholder="Enter Name To Filter" bind:value={choosenPerson}>
<br>

<input type="text" placeholder="Enter Name" bind:value={person.name}>
<input type="text" placeholder="Enter Age" bind:value={person.age}>

<button onclick={appendToPersons}>Append To Person</button>

<button onclick={() => persons.pop()}>Delelte Latest Persons</button>
<button onclick={() => animals.pop()}>Delete Latest Animal</button>

<button onclick={() => {
  persons.sort((a, b) => a.name.localeCompare(b.name));
}}>Sort Array</button>

<div>
    <p>Minors</p>
    {#each persons.filter(person => isMinor(person)) as person}
        <p>{person.name} is {person.age}'s years old</p>
    {/each}
    <p>Adults</p>
    {#each persons.filter(person => !isMinor(person)) as person}
        <p>{person.name} is {person.age}'s years old</p>
    {/each}
</div>

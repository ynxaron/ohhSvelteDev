<svelte:head>
   <title>Solutions To Section 6</title>
</svelte:head>

<script>
    let animals = $state(["Racoon", "Cat", "Panda", "Cat", "BlueBerries"]);
    let persons = $state([
      {name: "Aron", age: 21},
      {name: "Jessy", age: 16},
      {name: "Sherry", age: 19},
      {name: "Cherry", age: 24}
    ]);
    let person = $state({});

    const appendToName = () => {
      console.log(`The Name Is: ${person.name} and Age Is: ${person.age}`)
      if (!person.hasOwnProperty('name') || !person.hasOwnProperty('age')) {
        console.log(`Person Does not have 'name' property`);
        return;
      }
      persons.forEach((thisperson) => {
        console.log(`Person Does not have a unique name`);
        if (thisperson.name == person.name) {
          return;
        }
      })
      persons.push({name: person.name, age: person.age});
    }

    const colors = ["Red", "Blue", "Green", "Yellow"];
    let color = $state(colors[0]);
</script>

<div style='background-color: {color}'>
    <ul>
        {#each animals as animal, i}
            <li>{animal}, {i}</li>
        {/each}
    </ul>

    <ul>
        {#each persons as person}
            <p>{person.name} is {person.age} years old</p>
        {/each}
    </ul>

    <input type="text" placeholder="Enter Name" bind:value={person.name}>
    <input type="text" placeholder="Enter Age" bind:value={person.age}>

    <button onclick={appendToName}>Append To Name</button>

    <select bind:value={color}>
        {#each colors as thiscolor}
            <option>{thiscolor}</option>
        {/each}
    </select>
</div>

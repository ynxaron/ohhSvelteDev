<svelte:head>
    <title>Special Solution To Section 7</title>
</svelte:head>

<script>
    const persons = $state([
      {name: "Satyam", age: 21},
      {name: "Aron", age: 22},
      {name: "Alice", age: 25},
      {name: "Michael", age: 26}
    ]);

    const shuffleRanking = function(rid, symbol)  {
      const id = Number(rid);
      const beforeRanking = id;
      let afterRanking = id;
      if (Number(symbol) == '1') {
        console.log('Adding Value');
        afterRanking = (id + 1) == persons.length ? 0 : (id + 1);
      } else {
        console.log('Subtracting Value');
        afterRanking = ((id - 1) == -1) ? persons.length - 1 : (id - 1);
      }

      console.log(`Before Rank Is ${beforeRanking} and after rank is ${afterRanking}`);

      console.log(`Before Ranking is ${beforeRanking} and Index value Is: ${persons[beforeRanking]}`);
      console.log(`After Ranking is ${afterRanking} and Index Index Is: ${persons[afterRanking]}`);

      [persons[beforeRanking], persons[afterRanking]] = [persons[afterRanking], persons[beforeRanking]];

    }
</script>

<div>
    {#each Object.entries(persons) as [id, person]}
        <div>
            <p>{person.name} is {person.age} years old</p>
            <button onclick={() => shuffleRanking(id, '1')}>DownGrade Ranking</button>
            <button onclick={() => shuffleRanking(id, '2')}>Upgrade Ranking</button>
        </div>
    {/each}
</div>

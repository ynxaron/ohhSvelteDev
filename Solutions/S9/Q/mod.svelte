<svelte:head>
    <title>Solutions To Section 9</title>
</svelte:head>

<script>
    import TextArea from './TextArea.svelte';
    import Slider from '@bulatdashiev/svelte-slider';
    let text = $state('');
    let userFeedback = $state({content: ''});
    let isChecked = $state(false);
    let colorPicked = $state('Red');
    let fruitsSelected = $state([]);

    let userInfo = $state({name: '', age: '', isStudent: false});

    let inputBindValue = $state('');

    let selectValue = $state('');

    const handlingFormValue = function(event) {
      event.preventDefault();
      console.log(`The Form Value Is: ${JSON.stringify(userInfo)}`);
    }

    let celebrityNames = $state([]);

    let liveProfileInfo = $state({name: '', age: '', isStudent: false});

    let sliderValue = $state([0, 0]);
</script>

<p>The Name Is: {text}</p>
<input type="text" placeholder="Enter Name" bind:value={text}>

<div>
    <p>The Feedback length is: {userFeedback.content.length}</p>
</div>

<TextArea {userFeedback}></TextArea>

<p>{isChecked}</p>
<label for="nameChecked">
    <p>Is Checked</p>
    <input type="checkbox" bind:checked={isChecked}>
    <label for="Is Checked">Is Checked</label>
</label>

<br>
<br>

<div>
    <p>The Color Picked Is: {colorPicked}</p>
    <form>
        <input type="radio" bind:group={colorPicked} value="Red">
        <label for="red">Red</label>
        <br>
        <input type="radio" bind:group={colorPicked} value="Blue">
        <label for="css">Blue</label>
        <br>
        <input type="radio" bind:group={colorPicked} value="Green">
        <label for="css">Green</label>
    </form>

    <br><br><br>

    <form>
        <input type="checkbox" value="Banana" bind:group={fruitsSelected}>
        <label for="bananaSelect">Banana</label>
        <br>
        <input type="checkbox" value="Apple" bind:group={fruitsSelected}>
        <label for="AppleSelect">Apple</label>
        <br>
        <input type="checkbox" value="Mangoes" bind:group={fruitsSelected}>
        <label for="MangoSelect">Mangoes</label>
    </form>

    <p>Total Fruits Picked Are: {fruitsSelected.join(', ')}</p>
</div>

<div>
    <select bind:value={selectValue}>
        <option>Satyam</option>
        <option>Aron</option>
        <option>Michael</option>
    </select>

    <p>The Value Is: {selectValue}</p>
</div>

<div>
    <p>Two Inputs Binded To Same Value</p>

    <input type="text" placeholder="Enter Name" bind:value={inputBindValue}>
    <input type="text" placeholder="Enter Age" bind:value={inputBindValue}>

    <p>Entered Value Is: {inputBindValue}</p>
</div>

<div>
    <form onsubmit={handlingFormValue}>
        <label for="name">Name</label>
        <input type="text" placeholder="Enter Name" bind:value={userInfo.name}>
        <br>
        <label for="age">Age</label>
        <input type="text" placeholder="Enter Age" bind:value={userInfo.age}>
        <br>
        <label for="isStudent">Is Student</label>
        <input type="checkbox" bind:checked={userInfo.isStudent}>
        <br>
        <input type="submit" placeholder="Submit Form">
    </form>
</div>

<div>
    {#if celebrityNames.length}
        <p>The Celebrity Names Are: {celebrityNames.join(',')}</p>
    {:else}
        <p>There Are No Celebrity Names</p>
    {/if}

    <input type="checkbox" value="Keanu" bind:group={celebrityNames}>
    <label for="keanu">Keanu Reaves</label>
    <br>

    <input type="checkbox" value="Zendaya" bind:group={celebrityNames}>
    <label for="zendaya">Zendaya</label>
    <br>

    <input type="checkbox" value="Ryan" bind:group={celebrityNames}>
    <label for="Ryan">Ryan Reynolds</label>
</div>

<div>
    <p>Live Profile Edit</p>
    <p>Name Is: {liveProfileInfo.name}</p>
    <p>Age Is: {liveProfileInfo.age}</p>

    {#if liveProfileInfo.isStudent}
        <p>You Are A Student</p>
    {:else}
        <p>You Work</p>
    {/if}

    <br><br>

    <input placeholder="Enter Name" bind:value={liveProfileInfo.name}>
    <br>
    <input placeholder="Enter Age" bind:value={liveProfileInfo.age}>
    <br>
    <input type="checkbox" bind:checked={liveProfileInfo.isStudent}>
    <label for="isStudent">Is Student</label>
</div>

<div>
    <p>The Slider Value Is: {sliderValue[0]}</p>
    <div style="background-color: red;
                height: {sliderValue[0] + 20}px;
                width: {sliderValue[0] + 20}px;
                border-radius: 50%"></div>
    <Slider bind:value={sliderValue}></Slider>
</div>

<!-- svelte-ignore a11y_autofocus -->
<script>
    let greenOrBlue = $state(true);
    let changeColor = () => {greenOrBlue = !greenOrBlue};
    // Decscribing Mouse Movements
    let mouseX = $state(0);
    let mouseY = $state(0);
    let mouseCord = (event) => {
      mouseX = event.clientX;
      mouseY = event.clientY;
    }
    let copyMessageVisible = $state(false);
    let toggleCopyMessage = () => {
      copyMessageVisible = true;
      setTimeout(() => copyMessageVisible = false, 2000);
    }
    let themeMode = $state('Light');
    const modes = ['Light', 'Dark'];

    let doubleClicked = $state(false);
    const clickDouble = function() {
      doubleClicked = true;
      setTimeout(() => doubleClicked = false, 1500)
    }
    let inputedText = $state('');
    let textSize = $state('10px');

    const randomizeNums = function() {
      textSize = `${100 * Math.random(5, 30)}px`;
    }
</script>
<style>
    .lightMode {
        background-color: white;
        color: black;
    }
    .darkMode {
        background-color: black;
        color: white;
    }
    .greetTextRed {
        color: red;
        font-size: "100px";
    }
    .greetTextBlue {
        color: blue;
        font-size: "100px";
    }
</style>

<div class={themeMode === "Light" ? "lightMode": "darkMode"}>
    <button onclick={changeColor}>Toggle Color</button>
    <p class={greenOrBlue ? "greetTextRed" : "greetTextBlue"} onmouseenter={changeColor} onmouseleave={changeColor}>Hello There</p>
    <div onmousemove={mouseCord}>
        <p>The Mouse Position At This Moment</p>
        <p>X Coordinate: {mouseX}</p>
        <p>Y Coordinate: {mouseY}</p>
    </div>

    <button onclick={toggleCopyMessage}>Copy Text</button>
    {#if copyMessageVisible}
        Copied!
    {/if}

    <br>
    <br>

    <p>The Current Mode Is: {themeMode}</p>
    <select bind:value={themeMode}>
        {#each modes as mode}
            <option value={mode}>{mode}</option>
        {/each}
    </select>

    <button ondblclick={clickDouble}>Double Click This Text</button>
    {#if doubleClicked}
        <p>You Clicked This Button Twice</p>
    {/if}

    <p>The Length Of '{inputedText}' is {inputedText.length}</p>
    <input bind:value={inputedText}>
    <hr>

    <p style="font-size: {textSize}">This is a headline</p>
    <p>{textSize}</p>
    <button onclick={randomizeNums}>Randomize Headline</button>
</div>

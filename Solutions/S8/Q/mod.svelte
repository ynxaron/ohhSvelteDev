<script>
    import { preventDefault } from "svelte/legacy";
    let count = $state(0);
    let blueOrBlack = $state(false);
    let text = $state('');

    const doSomething = function(val) {
      console.log(`Printing ${val}`);
    }
</script>

<button onclick={() => count++}>Click Me</button>
<button onclick={(e) => console.log(e.target)}>Click Me Again</button>
<button onclick={() => alert('This Button Has Been Clicked')}>Click This Button for alert</button>

<button onmouseenter={() => console.log('Mouse Has Entered')} onmouseleave={() => console.log('Mouse Has Left')}>Another Button</button>

<div style="background-color: {blueOrBlack ? 'blue' : 'black'}">
    <button onmouseenter={() => blueOrBlack = !blueOrBlack} onmouseleave={() => blueOrBlack = !blueOrBlack}>Change Color</button>
</div>

<button onkeydown={(key) => console.log(key.key)}>Key Button</button>


<div>
    <form onsubmit={() => {
      console.log("Hello There");
      preventDefault()
    }}
        <label for="valueAdding">Add Value
        <br>
        <input type="text" placeholder="Enter Value">
        <br>
        <input type="submit" value="Submit">
    </form>
</div>

<button ondblclick={() => console.log("You Double Clicked")}>You Double Clicked</button>
<button ondblclick={() => doSomething(32)}>Some Button</button>

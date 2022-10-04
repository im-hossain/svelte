<script>
    import Nested from "./Nested.svelte";


  let count = 0
  $: doubled = count * 2;
  const increment = () => {
    count += 1
  }
  const decrement =()=>{
    count -=1
  }
  $: if (count >= 10) {
		alert('count is dangerously high!');
		count = 9;
	}
  let numbers = [1, 2, 3, 4];

	function addNumber() {
		numbers= [...numbers, numbers.length+1]
	}

	$: sum = numbers.reduce((t, n) => t + n, 0);
		
</script>


<p>{count}</p>
<p>{count} doubled is {doubled}</p>
<button on:click={increment}>
  increment
</button>
<button on:click={decrement}>
  decrement
</button>
<p>{numbers.join(' + ')} = {sum}</p>
<button on:click={addNumber}>
  Add numbers
</button>

<Nested count={count}/>
<Nested />
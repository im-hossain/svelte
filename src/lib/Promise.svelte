<script>
  import { claim_svg_element } from "svelte/internal";


    const getTodo =async()=>{
        try {
            const response = await fetch('https://jsonplaceholder.typicode.com/tods/1')
            const result  = await response.json()
            if(response.ok){
                return result
            }else{
                throw new Error(result)
            }
        } catch (error) {
            console.log(JSON.stringify(error));
            throw new Error(error)
        }
        
    }
    let promise = getTodo()
    const handleClick= ()=>{
        promise = getTodo()
    }
</script>
<div>
    <button on:click={handleClick}>
        Get Todo
    </button>
    {#await promise}
	    <p>...waiting</p>
    {:then value}
	    <p>{JSON.stringify(value)}</p>
    {:catch error}
	    <p style="color: red">{JSON.stringify(error)}</p>
    {/await}
</div>
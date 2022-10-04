<script>
	let cats = [
		{ id: 'J---aiyznGQ', name: 'Keyboard Cat' },
		{ id: 'z_AbfPXTKms', name: 'Maru' },
		{ id: 'OUtn3pvWmpg', name: 'Henri The Existential Cat' }
	];
</script>

<ul>
    {#each cats as cat, i (cat.id)}
    <li> {i+1} -------------> {  cat.name }</li>
    {/each}
</ul>
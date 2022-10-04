<script>
  import Counter from './lib/Counter.svelte'
  import EachBlock from './lib/EachBlock.svelte';
  import ExpressionWithHtml from './lib/ExpressionWithHTML.svelte';
  import InfoContainer from './lib/InfoContainer.svelte';
  import Promise from './lib/Promise.svelte';
</script>

<main>
  <div class="card">
    <Counter />
    <InfoContainer/>
    <ExpressionWithHtml/>
    <EachBlock/>
    <!-- promise -->
    <Promise/>
  </div>
</main>

<script>
   import Story from './Story.svelte'
   export let stories = []
</script>

<ul class="px-4 py-3 flex space-x-4 overflow-x-auto">
   {#each stories as story, i}
      <Story {story} index={i} />
   {/each}
</ul>

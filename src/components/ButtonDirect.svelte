<script>
   import Icon from './Icon.svelte'

   export let direct = 0
</script>

<button class="relative">
   <Icon 
      class="h-6 w-6 transform rotate-45" 
      name="direct" 
   />
   {#if direct > 0}
      <span 
         class="absolute right-0 top-0 h-4 w-4 flex items-center justify-center bg-red text-xs text-white rounded-full"
      >
         {direct}
      </span>
   {/if}
</button>
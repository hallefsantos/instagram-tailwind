<script>
   import Icon from './Icon.svelte'

   let isFocused = false
   let searchInput

   function focus () {
      if(!searchInput.value > 0) {
         isFocused = !isFocused
      }
   }

   function clearInput () {
      searchInput.value = ''
      isFocused = false
   }
</script>

<div class="relative">
   <div 
      class="{ isFocused ? 'ml-2' : 'ml-16' } absolute inset-y-0 flex items-center opacity-40"
   >
      <Icon class="h-3 w-3" name="search"/>
   </div>
   <input 
      bind:this={searchInput}
      on:focus={focus} 
      on:focusout={focus} 
      class="{ isFocused ? 'text-left' : 'text-center' } py-1 px-6 w-52 bg-gray-light focus:outline-none border border-gray-dark text-sm rounded" 
      type="text" 
      placeholder="Search"
   >
   {#if isFocused}
      <div class="absolute right-1 inset-y-0 flex items-center">
         <button 
            on:click={clearInput}
            class="opacity-50 hover:opacity-90 transition duration-200">
            <Icon class="h-5 w-5" name="close"/>
         </button>
      </div>
   {/if}
</div>
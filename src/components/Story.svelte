<script>
   import Icon from './Icon.svelte'
   export let story = {}
   export let index = null
</script>

<li class="flex-shrink-0">
   <div class="text-center">
      <div class="{ index !== 0 ? 'bg-gradient-to-r from-orange via-pink to-purple' : '' } relative flex justify-center items-center rounded-full border-2 border-transparent">
         <img 
            class="h-14 w-14 object-cover object-center rounded-full border-2 border-white box-content" 
            src="{story.avatar}" 
            alt="@{story.username}"
         >
         {#if index === 0}
            <span class="absolute right-0 bottom-0 h-4 w-4 flex justify-center items-center bg-blue text-white rounded-full border border-gray-light">
               <Icon class="h-4 w-4" name="plus" />
            </span>
         {/if}
      </div>
      <span class="text-xs">
         {#if index === 0} Your story {:else} {story.username} {/if}
      </span>
   </div>
</li>
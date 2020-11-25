<script>
   import Icon from './Icon.svelte'
   export let username
</script>

<div class="flex items-start">
   <p class="flex-auto">
      <a class="font-bold" href="#">{username}</a>
      <slot />
   </p>
   <button class="ml-2">
      <Icon class="h-4 w-4" name="heart" />
   </button>
</div>
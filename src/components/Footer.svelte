<script>
   import Icon from './Icon.svelte'
   import ButtonProfile from './ButtonProfile.svelte'
   
</script>

<div class="fixed bottom-0 inset-x-0 px-3 py-2 flex sm:hidden justify-between shadow-lg bg-white border-t border-gray-light">
   <button>
      <Icon class="w-7 h-7" name="house"/>
   </button>

   <button>
      <Icon class="w-7 h-7" name="search"/>
   </button>

   <button>
      <Icon class="w-7 h-7" name="plus"/>
   </button>

   <button>
      <Icon class="w-7 h-7" name="heart"/>
   </button>

   <ButtonProfile />
</div>
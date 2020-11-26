<script>
   import Stories from './components/Stories.svelte'
   import Icon from './components/Icon.svelte'
   import Post from './components/Post.svelte'
   import ButtonDirect from './components/ButtonDirect.svelte'
   import ButtonProfile from './components/ButtonProfile.svelte'
   import Search from './components/Search.svelte'

   const direct = 9

   const stories = [
      {
         username: 'Your story',
         avatar: 'https://placekitten.com/61/60'
      },
      {
         username: 'user01',
         avatar: 'https://placekitten.com/60/61'
      },
      {
         username: 'user02',
         avatar: 'https://placekitten.com/62/60'
      },
      {
         username: 'user03',
         avatar: 'https://placekitten.com/60/62'
      },
      {
         username: 'user04',
         avatar: 'https://placekitten.com/63/60'
      },
      {
         username: 'user05',
         avatar: 'https://placekitten.com/60/63'
      },
      {
         username: 'user06',
         avatar: 'https://placekitten.com/64/60'
      },
      {
         username: 'user07',
         avatar: 'https://placekitten.com/60/64'
      },
      {
         username: 'user08',
         avatar: 'https://placekitten.com/65/60'
      },
      {
         username: 'user09',
         avatar: 'https://placekitten.com/60/65'
      },
      {
         username: 'user10',
         avatar: 'https://placekitten.com/66/60'
      },
   ]
</script>

<header class="fixed inset-x-0 px-4 py-2 shadow bg-white z-10">
   <div class="lg:m-auto lg:max-w-4xl flex justify-between items-center lg:grid lg:grid-cols-3">
      <div class="block lg:hidden">
         <button>
            <Icon class="h-6 w-6" name="camera" />
         </button>
      </div>

      <div class="">
         <a href="#">
            <img class="h-8" src="/src/images/logo.svg" alt="">
         </a>
      </div>

      <div class="flex justify-center">
         <Search />
      </div>

      <!-- Button Svelte -->
      <div class="flex items-center justify-end space-x-4">
         <button><Icon class="h-6 w-6" name="house" /></button>

         <ButtonDirect {direct} />

         <button><Icon class="h-6 w-6" name="map" /></button>

         <button><Icon class="h-6 w-6" name="heart" /></button>

         <ButtonProfile />
      </div>
      
   </div>
</header>

<div class="bg-gray-light pt-14 shadow">
   <Stories {stories} />
</div>

<main class="pb-8">
   <!-- Post -->
   <Post />
   <Post />
   <Post />
   <Post />
</main>

<div class="fixed bottom-0 inset-x-0 px-3 py-2 flex justify-between shadow-lg bg-white border-t border-gray-light">
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

<!-- TODO: Criar um component para as rounded-full-images deixando passar classe por parametro, img, alt -->
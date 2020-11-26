<script>
   import Icon from './Icon.svelte'
   import Comment from './Comment.svelte'
   import { fade, scale, slide } from 'svelte/transition'

   let isMenuActive = false
   let isShareActive = false

   const randProfile = Math.floor(Math.random() * (40 - 30 + 1) + 30)
   const randPicture = Math.floor(Math.random() * (500 - 350 + 1) + 350)
   console.log(randPicture)
</script>

<article class="mb-5">
   <header class="p-3">
      <div class="flex justify-between">
         <a href="#" class="flex items-center">
            <img class="h-8 w-8 rounded-full" src="https://placekitten.com/32/{randProfile}" alt="">
            <div class="ml-3 flex flex-col">
               <strong class="text-sm">gatinho.bonitinho</strong>
               <span class="text-xs">Gatolandia</span>
            </div>
         </a>

         <button on:click={() => isMenuActive = !isMenuActive}>
            <Icon class="h-4 w-4 opacity-80" name="dots"/>
         </button>

      </div>
   </header>
   <div>
      <img class="w-full" src="https://placekitten.com/420/{randPicture}" alt="">

      <div class="px-3">
         <div class="py-2 flex justify-between">
            <div class="space-x-4">
               <button>
                  <Icon class="w-7 h-7" name="heart" />
               </button>
               <button>
                  <Icon class="w-7 h-7" name="comments" />
               </button>
               <button>
                  <Icon class="w-7 h-7 transform rotate-45" name="direct" />
               </button>
            </div>

            <button>
               <Icon class="w-7 h-7" name="bookmark" />
            </button>
         </div>

         <div class="flex items-center mb-2">
            <img class="w-5 h-5 rounded-full" src="https://placekitten.com/21/21" alt="@user">
            <div class="ml-2 text-sm">
               Liked by <strong>miau</strong> and <strong>50,000 others</strong>
            </div>
         </div>

         <!-- Comments -->
         <div class="text-sm space-y-1">
            <!-- Main Comment -->
            <div>
               <p>
                  <a class="font-bold" href="#">jornaldosgatos</a>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus modi et, inventore, tenetur fuga autem adipisci velit ipsam iste placeat, rerum facilis voluptatem in veniam deleniti. Asperiores vitae tempora esse.
               </p>
            </div>

            <div>
               <a class="text-gray-dark" href="#">View all 3,567 comments</a>
            </div>

            <Comment username="helloworld">
               Lorem ipsum dolor sit amet consectetur adipisicing elit.
            </Comment>

            <Comment username="joselito">
               Lorem ipsum, dolor sit amet consectetur adipisicing elit. Voluptas eveniet nemo ut exercitationem facilis. Doloremque, delectus error. Quam tempore architecto vero voluptates, aliquam aperiam officiis quod, hic tenetur debitis eveniet!
            </Comment>
         </div>
      </div>
   </div>
   <footer class="px-3">
      <span class="text-gray-dark uppercase font-medium tracking-wide" style="font-size: .65rem">14 hours ago</span>
   </footer>
</article>

{#if isMenuActive}
   <div
      on:click={() => isMenuActive = !isMenuActive}
      transition:fade="{{ duration: 200 }}"
      class="fixed inset-0 flex justify-center items-center bg-black bg-opacity-70 z-20"
   >
      <div 
         transition:scale="{{ duration: 100, delay: 100, opacity: 0, start: 1.2 }}"
         class="bg-white rounded-xl overflow-hidden">
         <ul class="text-center text-sm">
            <li class="px-20 py-3 border-b border-gray-light">
               <a class="font-bold text-red" href="#">Report</a>
            </li>
            <li class="px-20 py-3 border-b border-gray-light">
               <a class="font-bold text-red" href="#">Unfollow</a>
            </li>
            <li class="px-20 py-3 border-b border-gray-light">
               <a href="#">Go to post</a>
            </li>
            <li class="px-20 py-3 border-b border-gray-light">
               <a on:click={() => isShareActive = !isShareActive} href="#">Share to...</a>
            </li>
            <li class="px-20 py-3 border-b border-gray-light">
               <a href="#">Copy link</a>
            </li>
            <li class="px-20 py-3 border-b border-gray-light">
               <a href="#">Embed</a>
            </li>
            <li class="px-20 py-3">
               <a href="#">Cancel</a>
            </li>
         </ul>
      </div>
   </div>
{/if}

{#if isShareActive}
   <div 
      on:click={() => isShareActive = !isShareActive}
      transition:fade="{{ duration: 200 }}"
      class="fixed flex items-end inset-0 bg-black bg-opacity-70 z-20"
   >
      <div 
         transition:slide="{{ duration: 750 }}"
         class="w-full bg-white rounded-xl rounded-bl-none rounded-br-none"
      >
         <!-- Share to -->
         <div class="flex items-center flex-col text-center border-b border-gray-dark py-3">
            <div class="w-10 h-1 rounded-md bg-gray-dark bg-opacity-60 mb-3"></div>
            <span class="font-medium">Share to...</span>
         </div>

         <ul class="p-4 space-y-5 text-sm">
            <li>
               <a class="flex items-center" href="#">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill="none" d="M0 0h24v24H0z"/><path d="M1.923 9.37c-.51-.205-.504-.51.034-.689l19.086-6.362c.529-.176.832.12.684.638l-5.454 19.086c-.15.529-.475.553-.717.07L11 13 1.923 9.37zm4.89-.2l5.636 2.255 3.04 6.082 3.546-12.41L6.812 9.17z"/></svg>
                  <span class="ml-2 block font-medium">Share to Direct</span>
               </a>
            </li>
            <li>
               <a class="flex items-center" href="#">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill="none" d="M0 0h24v24H0z"/><path d="M14 13.5h2.5l1-4H14v-2c0-1.03 0-2 2-2h1.5V2.14c-.326-.043-1.557-.14-2.857-.14C11.928 2 10 3.657 10 6.7v2.8H7v4h3V22h4v-8.5z"/></svg>
                  <span class="ml-2 block font-medium">Share to Facebook</span>
               </a>
            </li>
            <li>
               <a class="flex items-center" href="#">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill="none" d="M0 0h24v24H0z"/><path d="M7.764 19.225c.59-.26 1.25-.309 1.868-.139.77.21 1.565.316 2.368.314 4.585 0 8-3.287 8-7.7S16.585 4 12 4s-8 3.287-8 7.7c0 2.27.896 4.272 2.466 5.676a2.8 2.8 0 0 1 .942 2.006l.356-.157zM12 2c5.634 0 10 4.127 10 9.7 0 5.573-4.366 9.7-10 9.7a10.894 10.894 0 0 1-2.895-.384.8.8 0 0 0-.534.039l-1.984.876a.8.8 0 0 1-1.123-.707l-.055-1.78a.797.797 0 0 0-.268-.57C3.195 17.135 2 14.617 2 11.7 2 6.127 6.367 2 12 2zM5.995 14.537l2.937-4.66a1.5 1.5 0 0 1 2.17-.4l2.336 1.75a.6.6 0 0 0 .723 0l3.155-2.396c.421-.319.971.185.689.633l-2.937 4.66a1.5 1.5 0 0 1-2.17.4l-2.336-1.75a.6.6 0 0 0-.723 0l-3.155 2.395c-.421.319-.971-.185-.689-.633z"/></svg>
                  <span class="ml-2 block font-medium">Share to Messenger</span>
               </a>
            </li>
            <li>
               <a class="flex items-center" href="#">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill="none" d="M0 0h24v24H0z"/><path d="M7.253 18.494l.724.423A7.953 7.953 0 0 0 12 20a8 8 0 1 0-8-8c0 1.436.377 2.813 1.084 4.024l.422.724-.653 2.401 2.4-.655zM2.004 22l1.352-4.968A9.954 9.954 0 0 1 2 12C2 6.477 6.477 2 12 2s10 4.477 10 10-4.477 10-10 10a9.954 9.954 0 0 1-5.03-1.355L2.004 22zM8.391 7.308c.134-.01.269-.01.403-.004.054.004.108.01.162.016.159.018.334.115.393.249.298.676.588 1.357.868 2.04.062.152.025.347-.093.537a4.38 4.38 0 0 1-.263.372c-.113.145-.356.411-.356.411s-.099.118-.061.265c.014.056.06.137.102.205l.059.095c.256.427.6.86 1.02 1.268.12.116.237.235.363.346.468.413.998.75 1.57 1l.005.002c.085.037.128.057.252.11.062.026.126.049.191.066a.35.35 0 0 0 .367-.13c.724-.877.79-.934.796-.934v.002a.482.482 0 0 1 .378-.127c.06.004.121.015.177.04.531.243 1.4.622 1.4.622l.582.261c.098.047.187.158.19.265.004.067.01.175-.013.373-.032.259-.11.57-.188.733a1.155 1.155 0 0 1-.21.302 2.378 2.378 0 0 1-.33.288 3.71 3.71 0 0 1-.125.09 5.024 5.024 0 0 1-.383.22 1.99 1.99 0 0 1-.833.23c-.185.01-.37.024-.556.014-.008 0-.568-.087-.568-.087a9.448 9.448 0 0 1-3.84-2.046c-.226-.199-.435-.413-.649-.626-.89-.885-1.562-1.84-1.97-2.742A3.47 3.47 0 0 1 6.9 9.62a2.729 2.729 0 0 1 .564-1.68c.073-.094.142-.192.261-.305.127-.12.207-.184.294-.228a.961.961 0 0 1 .371-.1z"/></svg>
                  <span class="ml-2 block font-medium">Share to Whatsapp</span>
               </a>
            </li>
            <li>
               <a class="flex items-center" href="#">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill="none" d="M0 0h24v24H0z"/><path d="M15.3 5.55a2.9 2.9 0 0 0-2.9 2.847l-.028 1.575a.6.6 0 0 1-.68.583l-1.561-.212c-2.054-.28-4.022-1.226-5.91-2.799-.598 3.31.57 5.603 3.383 7.372l1.747 1.098a.6.6 0 0 1 .034.993L7.793 18.17c.947.059 1.846.017 2.592-.131 4.718-.942 7.855-4.492 7.855-10.348 0-.478-1.012-2.141-2.94-2.141zm-4.9 2.81a4.9 4.9 0 0 1 8.385-3.355c.711-.005 1.316.175 2.669-.645-.335 1.64-.5 2.352-1.214 3.331 0 7.642-4.697 11.358-9.463 12.309-3.268.652-8.02-.419-9.382-1.841.694-.054 3.514-.357 5.144-1.55C5.16 15.7-.329 12.47 3.278 3.786c1.693 1.977 3.41 3.323 5.15 4.037 1.158.475 1.442.465 1.973.538z"/></svg> 
                  <span class="ml-2 block font-medium">Share to Twitter</span>
               </a>
            </li>
            <li>
               <a class="flex items-center" href="#">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill="none" d="M0 0h24v24H0z"/><path d="M3 3h18a1 1 0 0 1 1 1v16a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V4a1 1 0 0 1 1-1zm17 4.238l-7.928 7.1L4 7.216V19h16V7.238zM4.511 5l7.55 6.662L19.502 5H4.511z"/></svg>
                  <span class="ml-2 block font-medium">Share via Email</span>
               </a>
            </li>
            <li>
               <a class="flex items-center" href="#">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill="none" d="M0 0h24v24H0z"/><path d="M13.06 8.11l1.415 1.415a7 7 0 0 1 0 9.9l-.354.353a7 7 0 0 1-9.9-9.9l1.415 1.415a5 5 0 1 0 7.071 7.071l.354-.354a5 5 0 0 0 0-7.07l-1.415-1.415 1.415-1.414zm6.718 6.011l-1.414-1.414a5 5 0 1 0-7.071-7.071l-.354.354a5 5 0 0 0 0 7.07l1.415 1.415-1.415 1.414-1.414-1.414a7 7 0 0 1 0-9.9l.354-.353a7 7 0 0 1 9.9 9.9z"/></svg>
                  <span class="ml-2 block font-medium">Copy Link</span>
               </a>
            </li>
            <li>
               <a class="flex items-center" href="#">
                  <svg class="opacity-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill="none" d="M0 0h24v24H0z"/><path d="M12 10.586l4.95-4.95 1.414 1.414-4.95 4.95 4.95 4.95-1.414 1.414-4.95-4.95-4.95 4.95-1.414-1.414 4.95-4.95-4.95-4.95L7.05 5.636z"/></svg>
                  <span class="ml-2 block font-medium">Cancel</span>
               </a>
            </li>
         </ul>
      </div>
   </div>
{/if}
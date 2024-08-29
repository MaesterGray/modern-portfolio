<script>
import { Navigation } from 'lucide-svelte';
import {projects} from '$lib'
import PinContainer from './ui/pin/PinContainer.svelte';
</script>

<div class="py-20">
    <h1 class="heading text-white">
      A small selection of{" "}
      <span class="text-purple">recent projects</span>
    </h1>
    <div class="flex flex-wrap items-center justify-center p-4 gap-16 mt-10">
        {#each projects as item}
        <div
        class="lg:min-h-[32.5rem] h-[25rem] flex items-center justify-center sm:w-96 w-[80vw]"
      >
        <PinContainer
          title="/ui.aceternity.com"
          href="https://twitter.com/mannupaaji"
        >
          <div class="relative flex items-center justify-center sm:w-96 w-[80vw] overflow-hidden h-[20vh] lg:h-[30vh] mb-10">
            <div
              class="relative w-full h-full overflow-hidden lg:rounded-3xl"
              style= "backgroundColor: #13162D"
            >
              <img src="/bg.png" alt="bgimg" />
            </div>
            <img
              src={item.img}
              alt="cover"
              class="z-10 absolute bottom-0"
            />
          </div>

          <h1 class="font-bold lg:text-2xl md:text-xl text-base line-clamp-1 text-white">
            {item.title}
          </h1>

          <p
            class="lg:text-xl lg:font-normal font-light text-sm line-clamp-2 text-[#BEC1DD] mx-[1vh] my-[0]"
           
          >
            {item.des}
          </p>

          <div class="flex items-center justify-between mt-7 mb-3">
            <div class="flex items-center">
              {#each item.iconLists  as icon,index}
              <div
                  class="border border-white/[.2] rounded-full bg-black lg:w-10 lg:h-10 w-8 h-8 flex justify-center items-center"
                  style= {`  transform: translateX(-${5 * index + 2}px)`} >
                  <img src={icon} alt="icon5" class="p-2" />
                </div>
              {/each}
            </div>

            <div class="flex justify-center items-center">
              <p class="flex lg:text-xl md:text-xs text-sm text-purple">
                Check Live Site
              </p>
              <Navigation class="ms-3" color="#CBACF9" />
            </div>
          </div>
        </PinContainer>
      </div>
        {/each}
      
    </div>
  </div>
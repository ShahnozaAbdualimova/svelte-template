<script>
    import { goto } from "$app/navigation";

    let businessDescription = "";
</script>

<main class="relative w-full h-full bg-black flex justify-center">
    <div class="max-w-7xl w-full px-6 md:px-12 lg:px-16 flex items-center">
    <div class="w-full lg:w-1/2 space-y-6 relative">
    <div class="background"></div> <!-- Background faqat chap taraf uchun -->
    <div class="inline-flex items-center gap-3 bg-white/10 backdrop-blur-md px-4 py-2 rounded-full">
        <span class="bg-[#9855FF] text-black text-xs font-semibold px-3 py-1 rounded-full">New</span>
        <span class="text-[#9855FF] text-sm">Latest integration just arrived</span>
    </div>
    <h1 class="text-7xl max-sm:text-5xl font-bold text-white bg-gradient-to-r from-white to-[#9855FF] text-transparent bg-clip-text">
        Create your own website
    </h1>
    <p class="text-gray-300 text-lg max-w-lg">
        Elevate your site’s visibility effortlessly with AI, where smart technology meets user-friendly SEO tools.
    </p>
    <div class="flex w-full max-w-md bg-white/10 p-2 rounded-lg backdrop-blur-md">
        <input 
            bind:value={businessDescription}
            type="text" 
            placeholder="Describe your business..."
            class="flex-1 bg-transparent outline-none text-white px-3 placeholder-gray-400"
        />
        <button class="bg-white text-black px-6 py-2 rounded-lg font-semibold" on:click={()=> goto("/request")}>Generate</button>
    </div>
    </div>


        <!-- O'ng taraf -->
        <div class="hidden lg:flex w-1/2 justify-end relative">
            <div class="relative bg-gradient-to-br from-[#9855FF] to-purple-600 p-6 rounded-3xl shadow-xl w-80 h-96 flex flex-col justify-end">
                <div class="absolute top-0 left-0 w-full h-full bg-black-900/60 rounded-3xl"></div>
                <div class="relative z-10 text-white">
                    <img src="/robot-2.png" alt="">    
                </div>
            </div>
            <!-- Gradient Box Effect -->
            <div class="absolute bottom-6 left-6 w-80 h-96 bg-[#9855FF]/40 blur-2xl rounded-3xl"></div>
        </div>
    </div>
</main>

<script lang="ts">
  import { onMount } from "svelte";

  type NavItem = {
    name: string;
    link: string;
    hasDropdown: boolean;
    submenu?: string[]; 
  };

  let navItems: NavItem[] = [
    { name: "Features", link: "#", hasDropdown: true, submenu: ["Feature 1", "Feature 2", "Feature 3"] },
    { name: "Developers", link: "/developers", hasDropdown: false },
    { name: "Company", link: "#", hasDropdown: true, submenu: ["About Us", "Careers", "Press"] },
    { name: "Blog", link: "/blog", hasDropdown: false },
    { name: "Changelog", link: "/changelog", hasDropdown: false }
  ];

  let openDropdown: number | null = null; 

  const toggleDropdown = function (index: number) {
    openDropdown = openDropdown === index ? null : index;
  };
</script>

<header class="text-white/60 p-4 relative">
    <div class="background"></div>
    <div class="container flex justify-between items-center border rounded-xl border-[#4c4c4d] py-2.5 px-4">
        <a href="/" class="relative flex items-center group">
            <img class="w-12 h-12 hover:cursor-pointer" src="/Logo.svg" alt="Logo">

             <span class="absolute left-full top-1/2 -translate-y-1/2 ml-2 px-3 py-1 rounded-lg bg-[#1a1a1a] text-white text-sm font-medium 
                 opacity-0 scale-90 group-hover:opacity-100 group-hover:scale-100 transition-all duration-300">
                  BuildifyAI
            </span>
        </a> 
        <nav>
            <ul class="flex space-x-6 text-lg relative">
                {#each navItems as item, index}
                    <li class="relative group">
                        <a href="{item.link}" class="flex items-center justify-items-center space-x-1 hover:text-white transition">
                            <span>{item.name}</span>
                            {#if item.hasDropdown}
                                <img 
                                src="/Vector.png" 
                                alt="Dropdown icon" 
                                class="transform: rotate({openDropdown === index ? '180deg' : '0deg'}); transition: transform 0.3s ease;"
                            />
                            {/if}
                        </a>
                        <!-- **Dropdown Menu** -->
                        {#if item.hasDropdown && item.submenu}
                            <ul class="absolute left-0 mt-2 w-40 z-50 bg-[#1a1a1a] text-white text-sm rounded-md shadow-lg opacity-0 group-hover:opacity-100 transition-all transform scale-95 group-hover:scale-100">
                                {#each item.submenu as subItem}
                                    <li class="px-4 py-2 hover:bg-[#2a2a2a]">
                                        <a href="#">{subItem}</a>
                                    </li>
                                {/each}
                            </ul>
                        {/if}
                    </li>
                {/each}
            </ul>
        </nav>

        <button class="text-white px-4 py-2 font-medium rounded-full border border-[#8C45FF]/100 bg-gradient-to-b from-[#8C45FF] to-[#4C1D95] shadow-lg overflow-hidden hover:opacity-100 opacity-90 transition text-base">
            Join waitlist
        </button>
    </div>
</header>

<style>
    .background {
        position: absolute;
        top: 0;
        left: 0;
        background-color: #000;
        background-image: linear-gradient(to right, rgba(205, 203, 203, 0.1) 1px, transparent 2px),
                          linear-gradient(to bottom, rgba(205, 203, 203, 0.1) 1px, transparent 2px);
        background-size: 7px 7px;
        height: 100%;
        width: 100% !important;
        z-index: -99;
    }
</style>
<slot></slot>
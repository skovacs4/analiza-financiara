<script>
  let menuOpen = false;

  const toggleMenu = () => {
    menuOpen = !menuOpen;
    console.log("Menu Open:", menuOpen);
  };
</script>

<!-- Navbar -->
<nav
  class="bg-[#050937] px-6 py-4 md:px-8 flex items-center justify-center gap-[250px]"
>
  <!-- Logo -->
  <div class="flex items-center space-x-2">
    <a href="/" class=""
      ><img src="/logo/logo-meniu.png" alt="AFA Logo" class="h-auto w-[125px]" /></a
    >
  </div>

  <!-- Desktop Nav Links -->
  <ul
    class="hidden md:flex items-center gap-[75px] text-white font-medium text-sm tracking-wide"
  >
    <li><a href="/" class="hover:underline">ACASĂ</a></li>
    <li><a href="/avantaje" class="hover:underline">AVANTAJE</a></li>
    <li><a href="/suport" class="hover:underline">SUPORT</a></li>
    <li><a href="/contact" class="hover:underline">CONTACT</a></li>
  </ul>

  <!-- CTA Button (desktop only) -->
  <a
    href="/inregistrare"
    class="hidden md:inline-block bg-[#E0E5F9] text-[#050937] text-lg font-medium px-6 py-4 rounded-full hover:bg-[#d6dbf0] transition"
  >
    Înregistrează-te
  </a>

  <!-- Burger Icon (mobile only) -->
  <button
    class="z-20 md:hidden text-white focus:outline-none"
    on:click={toggleMenu}
    aria-label="Toggle menu"
  >
    <svg
      class="h-6 w-6"
      fill="none"
      stroke="currentColor"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
    >
      {#if !menuOpen}
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M4 6h16M4 12h16M4 18h16"
        />
      {:else}
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M6 18L18 6M6 6l12 12"
        />
      {/if}
    </svg>
  </button>
</nav>

<!-- Mobile Menu -->
{#if menuOpen}
  <ul
    class="md:hidden bg-[#050937] px-6 pb-4 space-y-2 text-white text-sm font-medium"
  >
    <a href="/" class="block hover:underline">ACASĂ</a>
    <a href="/avantaje" class="block hover:underline">AVANTAJE</a>
    <a href="/suport" class="block hover:underline">SUPORT</a>
    <a href="/contact" class="block hover:underline">CONTACT</a>
  </ul>
{/if}

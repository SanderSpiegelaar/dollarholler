<script lang="ts">
    import { page } from '$app/stores';
    import Close from '$lib/components/icons/Close.svelte';
    import Hamburger from '$lib/components/icons/Hamburger.svelte';

    let isNavShowing: boolean = false;
</script>


<svelte:head>
    {#if isNavShowing}
        <style lang="postcss">
            body {
                @apply overflow-hidden md:overflow-auto;
            }
        </style>
    {/if}
</svelte:head>

<!-- Mobile Nav Control -->
<button class="fixed right-6 top-6 z-navBarToggle md:hidden"
        class:text-goldenFizz={isNavShowing}
        class:text-daisyBush={!isNavShowing}
        on:click={() => {isNavShowing = !isNavShowing}}
        >
    {#if isNavShowing}
        <Close width={32} height={32} />
    {:else}
        <Hamburger />
    {/if}
</button>

<header
    class="fixed z-navBar md:relative w-full h-screen md:col-span-3 -translate-x-full md:translate-x-0 bg-daisyBush text-center transition-transform"
    class:translate-x-0={isNavShowing}
    >
    <div class="mt-10 mb-10 md:mb-24">
      <a href="/"><img src="/images/logo.svg" alt="The Dollar Holler" class="mx-auto" /></a>
    </div>

    <nav>
      <ul class="list-none text-2xl font-bold">
        <li><a href="/invoices" class:active={$page.url.pathname === '/invoices'}>Invoices</a></li>
        <li><a href="/clients" class:active={$page.url.pathname === '/clients'}>Clients</a></li>
        <li><a href="#" class:active={$page.url.pathname === '/settings'}>Settings</a></li>
        <li><a href="#">Logout</a></li>
      </ul>
    </nav>
</header>

<style lang="postcss">
    nav ul li {
        @apply mb-6;
    }

    nav ul li a {
        @apply font-bold text-white hover:text-goldenFizz;
    }

    nav ul li a.active {
        @apply text-robinEggBlue px-8 transition-[padding];
        background: url('/images/active-nav--left.svg') left top no-repeat, url('/images/active-nav--right.svg') right top no-repeat;
    }

    nav ul li a.active:hover {
        @apply px-9;
    }
</style>
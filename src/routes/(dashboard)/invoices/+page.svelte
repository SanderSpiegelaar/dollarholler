<script lang="ts">
    import Search from '$lib/components/Search.svelte';
    import Tag from '$lib/components/Tag.svelte';
    import View from '$lib/components/icons/View.svelte';
    import ThreeDots from '$lib/components/icons/ThreeDots.svelte';
    import CircledAmount from '$lib/components/CircledAmount.svelte';
</script>


<svelte:head>
    <title>Invoices | The Dollar Holer</title>
</svelte:head>



<div class="flex justify-between items-center mb-16">
    <!-- Search Field -->
    <Search />
    <!-- New Invoice -->
    <div>
        <button class="relative whitespace-nowrap rounded-lg bg-lavenderIndigo px-10 py-3 font-sansSerif text-xl font-black text-white shadow-colored hover:shadow-coloredHover translate-y-0 hover:-translate-y-2 transition-all">+ Invoice </button>
    </div>
</div>

<!-- List of invoices -->
<div>
    <!-- Header -->
    <div class="table-header invoice-table text-daisyBush">
        <h3>Status</h3>
        <h3>Due Date</h3>
        <h3>ID</h3>
        <h3>Client</h3>
        <h3>Amount</h3>
        <div />
        <div />
    </div>

    <!-- Invoices -->
    <div class="invoice-table items-center bg-white py-6 rounded-lg shadow-tableRow">
        <div class="text-lg"><Tag label="draft"/></div>
        <div class="text-lg">12/1/2023</div>
        <div class="text-lg">1234</div>
        <div class="text-xl font-bold">Compressed.fm</div>
        <div class="text-lg font-bold font-mono">$1234.00</div>
        <div class="text-lg center"><a class="text-pastelPurple hover:text-daisyBush" href=""><View /></a></div>
        <div class="text-lg center"><button class="text-pastelPurple hover:text-daisyBush"><ThreeDots /></button></div>
    </div>
</div>

<!-- Total -->
<CircledAmount label="Total" amount="$1234.00" />

<style lang="postcss">
    .table-header h3 {
        @apply text-xl font-black leading-snug;
    }
</style>
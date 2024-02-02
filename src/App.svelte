<script lang="ts">
    const binRegex = /^[01]*$/;

    let bin = '';
    $: dec = parseInt(bin, 2);
    $: valid = binRegex.test(bin)
</script>

<h1 class="text-5xl font-semibold mb-5">Bin2Dec</h1>
<h2>Enter a binary number:</h2>
<input
    type="text"
    class="bg-black text-white ring-1 p-3 text-xl mt-3 ring-white focus:ring-blue-600 focus:outline-none"
    bind:value={bin}
/>

{#if valid && bin.length > 0}
    <p class="mt-5 text-xl font-semibold">Decimal: {dec}</p>
{/if}

{#if !valid}
  <p class="text-red-500 mt-5">Invalid binary number.</p>
{/if}
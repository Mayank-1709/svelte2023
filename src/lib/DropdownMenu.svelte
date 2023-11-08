<script>
    // Define the list of page options
    let pageOptions = [
      { value: '', label: 'CLICK ME' },
      { value: '/', label: 'Home' },
      { value: '/gallery', label: 'Gallery' },
      { value: '/stats', label: 'Stats' },
    ];
</script>
  
<select id="pageSelector" onchange="window.location.href = this.value;">
    {#each pageOptions as option}
        <option value={option.value}>{option.label}</option>
    {/each}
</select>
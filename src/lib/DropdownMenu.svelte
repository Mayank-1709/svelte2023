<script>
    // Define the list of page options
    let pageOptions = [
      { value: '/', label: 'Home' },
      { value: '/gallery', label: 'Gallery' },
      { value: '/stats', label: 'Stats' },
      // Add more options for other pages as needed
    ];
</script>
  
  <label for="pageSelector">Go to:</label>
  <select id="pageSelector" onchange="window.location.href = this.value;">
    {#each pageOptions as option}
      <option value={option.value}>{option.label}</option>
    {/each}
  </select>
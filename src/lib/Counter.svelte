<script>
  let count = 0;
  const increment = () => {
    count += 1;
  };

  export let deactivated;
</script>

<button disabled={deactivated} on:click={increment}>
  {count}
</button>

<style>
  button {
    background-color: #f9396b; /* Green */
    border: none;
    color: white;
    padding: 30px 64px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 32px;
    transition: transform 50ms ease-out;
    touch-action: manipulation;
    user-select: none;
  }

  button:active {
    transform: scale(1.4);
  }
</style>

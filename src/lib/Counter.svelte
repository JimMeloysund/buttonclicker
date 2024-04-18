<script>
  let count = 0;
  const increment = () => {
    count += 1;
  };
</script>

<button on:click={increment}>
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
  }

  button:active {
    transform: scale(1.4);
  }
</style>

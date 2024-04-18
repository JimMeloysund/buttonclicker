<script>
  import svelteLogo from "./assets/svelte.svg";
  import viteLogo from "/vite.svg";
  import Counter from "./lib/Counter.svelte";

  import { onMount } from "svelte";
  let timerStarted = false;
  let startTime;
  let elapsedTime = 0;
  let countdown = 30;
  const timeleft = 30;
  let hasstarted = false;

  const handleStart = () => {
    if (!hasstarted) {
      hasstarted = true;
      startTimer();
    }
  };

  const startTimer = () => {
    if (!timerStarted) {
      startTime = Date.now();
      timerStarted = true;
      const timerInterval = setInterval(() => {
        elapsedTime = Date.now() - startTime;
        countdown = Math.max(0, timeleft - Math.floor(elapsedTime / 1000));
        if (countdown === 0) {
          stopTimer();
          gameOver = true;
        }
      }, 10);
      return timerInterval;
    }
  };
  const stopTimer = () => {
    clearInterval(timerInterval);
    timerStarted = false;
  };
  let timerInterval;
  // onMount(() => {
  //   timerInterval = startTimer();
  // });
</script>

<main>
  <h2>Trykk så mange gang du klarer på {timeleft} Sekunder!</h2>
  <h2>{countdown}</h2>
  <div on:click={handleStart} class="card">
    <Counter />
  </div>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>

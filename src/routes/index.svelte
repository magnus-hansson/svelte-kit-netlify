<script>
  import Counter from "$components/Counter.svelte";
  import { count } from "../stores.js";
  import Incrementer from "$components/Incrementer.svelte";
  import Decrementer from "$components/Decrementer.svelte";
  import Resetter from "$components/Resetter.svelte";

  let count_value;

  const unsubscribe = count.subscribe(value => {
    count_value = value;
  });
</script>

<main>
  <h1>Hello world!!! YOLO</h1>

  <Counter />
  <p>
    Visit the <a href="https://svelte.dev">svelte.dev</a> to learn how to build Svelte
    apps.
  </p>

  <h1>The count is {count_value}</h1>

  <Incrementer />
  <Decrementer />
  <Resetter />
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4rem;
    font-weight: 100;
    line-height: 1.1;
    margin: 4rem auto;
    max-width: 14rem;
  }

  p {
    max-width: 14rem;
    margin: 2rem auto;
    line-height: 1.35;
  }

  @media (min-width: 480px) {
    h1 {
      max-width: none;
    }

    p {
      max-width: none;
    }
  }
</style>

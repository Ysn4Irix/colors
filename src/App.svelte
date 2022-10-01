<script>
  import { onMount } from 'svelte/internal'

  import Color from './components/Color.svelte'

  let color = ''

  const generateHex = () => {
    const chars = '0123456789ABCDEF'
    color = '#'
    for (let i = 0; i < 6; i++) {
      color += chars[Math.floor(Math.random() * 16)]
    }
  }

  onMount(() => generateHex())
</script>

<main>
  <h1>Colors</h1>
  <p class="text">
    <button on:click={generateHex} class="generator-button"> Click </button> to generate
    a new color
  </p>
  <div class="colors">
    <Color {color} />
  </div>
</main>

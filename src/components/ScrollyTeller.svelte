<Scroller
  top={0.0}
  bottom={1}
  threshold={0.5}
  bind:count
  bind:index
  bind:offset
  bind:progress
>
  <div class="background" slot="background">
    <div class="progress-bars">
      <p>current section: <strong>{index + 1}/{count}</strong></p>
      <progress value={count ? (index + 1) / count : 0} />

      <p>offset in current section</p>
      <progress value={offset || 0} />

      <p>total progress</p>
      <progress value={progress || 0} />
    </div>
  </div>

  <div class="foreground" slot="foreground">

      <section>This is the first section.</section>
      <section>This is the second section.</section>
      <section>This is the third section.</section>
    </div>

</Scroller>

<script>
    import { onMount } from 'svelte';
    import Scroller from "@sveltejs/svelte-scroller";

    let count, index, offset, progress;
  
    export let slides = [];
    let currentSlide = 0;
    let throttleTimeout = null; // Throttling scroll events
    const throttlePeriod = 1000; // controls the execution rate of a function
  
    function handleScroll(event) {
      event.preventDefault(); // Prevent page scrolling
  
      if (throttleTimeout) return; // Throttle scroll events
  
      const direction = event.deltaY > 0 ? 'down' : 'up';
      changeSlide(direction);
  
      throttleTimeout = setTimeout(() => {
        clearTimeout(throttleTimeout);
        throttleTimeout = null;
      }, throttlePeriod);
    }
  
    function changeSlide(direction) {
      if (direction === 'down' & currentSlide !== slides.length - 1) {
        currentSlide = (currentSlide + 1) % slides.length;
      } else if (direction === 'up' & currentSlide !== 0) {
        currentSlide = (currentSlide - 1 + slides.length) % slides.length;
      }
    }
    
    // wheel: fires when the user scrolls using their mouse wheel or trackpad
    onMount(() => {
      window.addEventListener('wheel', handleScroll, { passive: false });
  
      return () => {
        window.removeEventListener('wheel', handleScroll);
      };
    });
  </script>
  
  <img src={slides[currentSlide]} alt={`Slide ${currentSlide + 1}`} class="slide-image">
  
  <style>
    .slide-image {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      max-width: 90%;
      max-height: 90vh;
    }
  </style>
  
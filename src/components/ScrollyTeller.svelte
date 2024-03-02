<Scroller
  top={0.0}
  bottom={1}
  threshold={0.5}
  bind:count
  bind:index
  bind:offset
  bind:progress
>
  <div class="background" slot="background" >
    <div class="progress-bars">

      <!-- <p>till next page</p> -->
      <progress value={offset || 0} />

      <!-- <p>total progress</p>
      <progress value={progress || 0} /> -->
    </div>
  </div>

  <div class="foreground" slot="foreground" >

    <section> 1  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 2  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 3  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 4  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 5  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 6  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 7  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 8  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 9  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>

    </div>

</Scroller>

<script>
    import Scroller from "@sveltejs/svelte-scroller";

    let count, index, offset, progress;
  
    export let slides = [];

  </script>
  
  
  <style>
    .slide-image {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      max-width: 90%;
      max-height: 90vh;
    }

	[slot="background"] {
		background-color: rgba(97, 36, 36, 0);
		border-top: 2px solid #ff400000;
		border-bottom: 2px solid #ff400000;
		font-size: 1.4em;
		overflow: hidden;
		padding: 1em;
    transform: scale(0.7) translate(-20%, -30%);
	}
	
	[slot="background"] p {
		margin: 0;
	}
	
	[slot="foreground"] {
		pointer-events: none;
	}
	
	[slot="foreground"] section {
		pointer-events: all;
	}
	
	section {
		height: 80vh;
		background-color: rgba(0,0,0,0);
		color: white;
		padding: 1em;
		margin: 0 0 2em 0;
	}
  </style>
  
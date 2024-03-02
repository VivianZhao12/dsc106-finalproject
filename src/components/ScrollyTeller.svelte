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


    <section> <h1 class="topic">To Snitch or Not to Snitch: That is the Question</h1>
        <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image1">
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
    <section> 10  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 11  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 12  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 13  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>
    <section> 14  <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    </section>

    </div>

</Scroller>

<script>
    import Scroller from "@sveltejs/svelte-scroller";

    let count, index, offset, progress;
  
    export let slides = [];

  </script>
  
  
  <style>
    .topic {
      position: fixed;
      text-align: center;
      max-height: 90vh;
      font-family: "Rye", serif;
      font-weight: 400;
      font-style: normal;
      font-size: 50px;
    }
    


    .slide-image {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      max-width: 90%;
      max-height: 90vh;
    }
    .slide-image1 {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) ;
      max-width: 90%;
      max-height: 90vh;
    }



	[slot="background"] {
    position: fixed;
		background-color: rgba(0, 0, 0, 0);
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
/* 	
	[slot="foreground"] section {
		pointer-events: all;
	} */
	
	section {
		height: 80vh;
		background-color: rgba(0, 0, 0, 0);
		color: rgb(7, 0, 0);
		padding: 1em;
		margin: 0 0 2em 0;
	}

  </style>
  
<Scroller
  top={0.0}
  bottom={1}
  threshold={0.5}

  bind:index
  bind:offset

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

    <!-- <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image"> -->

    
  
  

    <!-- {:else if index === 10}
    <svg class = 'button' width="300" height="300" xmlns="http://www.w3.org/2000/svg">
      <rect width="150" height="150" x="10" y="10" rx="0" ry="0" />
    </svg>      

    <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image2">

    {:else if index === 12}
    <svg class = 'button' width="300" height="300" xmlns="http://www.w3.org/2000/svg">
      <rect width="150" height="150" x="10" y="10" rx="0" ry="0"  />
    </svg>  
    <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image2">

    {:else}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
    {/if} -->

    
    <section> 1
      {#if index === 0}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image1">
      <h1 class="topic">To Snitch or Not to Snitch: That is the Question</h1>
        <p class="text1-1">You 🐱 committed a minor crime with your friend 🐶 and were sentenced to 1 year of prison . Now 👮🏻 suspect that you two committed a more serious crime other than this. You two have been arrested and put in separate rooms. </p>
        <br>
        <br>
        <p class="text1-2"> You can either <bold class = 'bolded'>stay silent (cooperate)</bold> or <bold class = 'bolded'>betray (defect).</bold> </p>
      {/if}
    </section>
    <section> 2  
      {#if index === 1}
      <p class="text2">You can’t talk to each other, and you have no idea whether your friend stays silent or testifies against you.
      </p>
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image2">
      {/if}
    </section>
    <section> 3  
      {#if index === 2}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
      {/if}
    </section>
    <section> 4  
      {#if index === 3}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
      {/if}
    </section>
    <section> 5 
      {#if index === 4}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
      {/if}
    </section>
    <section> 6  
      {#if index === 5}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
      {/if}
    </section>
    <section> 7 
      {#if index === 6}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
      {/if}
    </section>
    <section> 8 
      {#if index === 7}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image"> 
      {/if}
    </section>
    <section> 9  
      {#if index === 8}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
      {/if}
    </section>
    <section> 10 
      {#if index === 9}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
      {/if}
    </section>
    <section id="slide-10"> 11  
      {#if index === 10}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
      {/if}
    </section>
    <section> 12  
      {#if index === 11}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
      {/if}
    </section>
    <section id="slide-12"> 13  
      {#if index === 12}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
      {/if}
    </section>
    <section> 14  
      {#if index === 13}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image">
      {/if}
    </section>
   

    </div>

</Scroller>

<script>
    import Scroller from "@sveltejs/svelte-scroller";

    let count, index, offset, progress;
    import { onMount } from 'svelte';
    import * as d3 from 'd3';
  
    export let slides = [];

    onMount(() => {
    // We only want to add the clickers when the slide with the index 9 or 11 is active
    });

  
    $: {
      if (index === 10) {
        createClickers('#slide-10');
      } else if (index === 12) {
        createClickers('#slide-12');
        }
      }

    function createClickers(slideElementId) {
    const svg = d3.select(slideElementId).select('svg'); // Assuming each slide has an inline SVG element

    // Define the coordinates and sizes for the "Cooperate" and "Defect" clickers
    const clickersData = [
      { id: 'cooperate', x: 10, y: 10, width: 100, height: 50, color: 'green' },
      { id: 'defect', x: 120, y: 10, width: 100, height: 50, color: 'red' }
    ];

    // Bind the clickers data to the rectangles
    const clickers = svg.selectAll('rect.clicker')
      .data(clickersData, d => d.id);

    console.log('here')  

    // Enter selection: Create rectangles if they don't exist yet
    clickers.enter()
      .append('rect')
      .attr('class', 'clicker')
      .attr('x', d => d.x)
      .attr('y', d => d.y)
      .attr('width', d => d.width)
      .attr('height', d => d.height)
      .attr('fill', 'transparent')
      .attr('stroke', 'black')
      .style('cursor', 'pointer')
      .on('click', function(event, d) {
        alert(`Clicked on ${d.id}`);
      })
      .on('mouseover', function(event, d) {
        d3.select(this).attr('fill', d.color);
      })
      .on('mouseout', function() {
        d3.select(this).attr('fill', 'transparent');
      });
  }


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
      transform: translate(1%, 100%);
    }
    
    .text1-1 {
      position: fixed;
      text-align: center;
      max-height: 90vh;
      font-size: 30px;
      transform: translate(10%, 150%);
      max-width: 80%;
    }

    .text1-2 {
      position: fixed;
      /* text-align: center; */
      max-height: 90vh;
      font-size: 30px;
      transform: translate(40%, 800%);
      max-width: 80%;
    }

    .text2 {
      position: fixed;
      text-align: center;
      max-height: 90vh;
      font-size: 30px;
      transform: translate(10%, 200%);
      max-width: 80%;
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
      transform: translate(-50%, -10%) scale(40%);
      max-width: 90%;
      max-height: 90vh;
    }

    .slide-image2 {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -40%) scale(90%);
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
  .bolded {
    font-weight: bold;
  }

  .button {
    position: fixed;
    transform: translate(158%, 137%);
    z-index: 1;
    display: block
	}
  
  </style>
  
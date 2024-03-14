<!-- <h1 class = 'index'></h1> -->

<svelte:body use:lockscroll={locked} />

<Scroller 
  top={0.0}
  bottom={1}
  threshold={0}

  bind:index
  bind:offset
>
  <div class="background" slot="background" >
    <div class="progress-bars">

      <!-- <p>till next page</p > -->
      <progress value={offset || 0} />

      <!-- <p>total progress</p >
      <progress value={progress || 0} /> -->
    </div>
  </div>
  <div class="foreground" slot="foreground" >
    <div class:scroll-lock={disabledScroll}>

      {#if index === 0}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image1">
      <p class="topic">To Snitch or Not to Snitch: That is the Question<p>
        <p class="text1-1">You 🐱 committed a minor crime with your friend 🐶 and were sentenced to <bold class = 'bolded'>1 year of prison</bold>. Now 👮🏻 suspect that you two <bold class = 'bolded'>committed another crime</bold>. You two have been arrested and put in separate rooms. </p >

        <br>
        <br>
        <p class="text1-2"> You can either <bold class = 'bolded'>stay silent (cooperate)</bold> or <bold class = 'bolded'>betray (defect).</bold> </p >
          {/if}
      
      {#if index === 1}
      <p class="text2"><bold class = 'bolded'>You can’t talk to each other</bold>, and you have no idea whether your friend <bold class = 'bolded'>stays silent (cooperate)</bold> or <bold class = 'bolded'>betrays (defect)</bold>
        you.
      </p >
  
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image2">
      {/if}
  
      {#if index === 2}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image3">
      <p class="text3">If <bold class = 'bolded'>you choose to betray (defect)</bold> by admitting your friend committed the crime, and <bold class = 'bolded'>your friend chooses to stay silent (cooperate)</bold>, you will go free. But your friend will be sentenced to 3 years of prison.</p >
        {/if}
  
      {#if index === 3}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image4">
      <p class="text4">But if <bold class = 'bolded'>you stay silent (cooperate)</bold>, and <bold class = 'bolded'>your friend betrays (defect)</bold>
        you, you’ll have to spend 3 years in prison and your friend goes free.</p >
      {/if}
  
      {#if index === 4}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image5">
      <p class="text5">If <bold class = 'bolded'>both of you choose to betray (defect)</bold>, you will both have to stay in prison for 2 years.
      </p >
  
      {/if}
  
      {#if index === 5}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image6">
      <p class="text6">If <bold class = 'bolded'>both of you stay silent (cooperate)</bold>, you both spend 1 year in prison only for the minor crime you are already charged with.
      </p >
  
      {/if}
  
      {#if index === 6}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image7">
      <h2 class="text7">Let’s Summarize them into a Matrix:</h2 >
      {/if}
  
      {#if index === 7}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image8"> 
      <p class="text8">If <bold class = 'bolded'>both of you stay silent (cooperate)</bold>, you both spend 1 year in prison.</p >
        {/if}
  
      {#if index === 8}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image9">
      <p class="text9">If <bold class = 'bolded'>one of you betray (defect)</bold>, the betrayer goes free and the one who stays silent (cooperate) spends 3 years in prison.</p >
        
          {/if}
  
      {#if index === 9}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image10">
      <p class="text10">If <bold class = 'bolded'>both of you betray (defect)</bold>, both of you spend 2 years in prison.</p >
        {/if}
  
      {#if index === 10 && (!click_cooperate1) && (!click_defect1)}
      <img src={'interact_given_cooperate.svg'} alt={`Slide ${index + 1}`} class="slide-image11">
      <p class="text11">What’s the best move if you think your friend is going to <bold class = 'bolded'>stay silent (cooperate)</bold>?
      </p >  
      {/if}
  
      {#if (index === 10) && (click_cooperate1) && (!click_defect1)}
      <img src={'outcome_given_cooperate.svg'} alt={`Slide ${index + 1}`} class="slide-image12">
      <p class="text12-1">If <bold class = 'bolded'>you choose to stay silent (cooperate)</bold>, you will still stay in prison for 1 year. 
      </p >
      <p class="text12-2"><bold class = 'bolded'>BUT!</bold> Choosing to <bold class = 'bolded'>betray (defect)  will free you instead.</bold>
        Therefore, the best move (assuming your friend will cooperate) is to defect them, so that you can be free.
      </p>
  
      {/if}
  
      {#if (index === 10) && (!click_cooperate1) && (click_defect1)}
      <img src={'outcome_given_cooperate.svg'} alt={`Slide ${index + 1}`} class="slide-image12-2">
      <h3 class='great_job'>Great Job!</h3>
      <p class="text12">
        Since <bold class = 'bolded'>betraying (defect)</bold> will exempt you from going to jail, it’s reasonable why you choose to defect!
        </p >  
      {/if}
  
  
      {#if index === 11 && (!click_cooperate2) && (!click_defect2)}
        <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image13">
        <p class="text11">What’s the best move if you think <bold class = 'bolded'>your friend is going to defect?</bold>
        </p >
  
      {/if}
  
      {#if (index === 11) && (click_cooperate2) && (!click_defect2)}
      <img src={'outcome_given_defect.svg'} alt={`Slide ${index + 1}`} class="slide-image12">
      <p class="text12-1"> If <bold class = 'bolded'>you choose to stay silent (cooperate)</bold>, you will still stay in prison for 3 years. 
      </p >
      <p class="text12-2"><bold class = 'bolded'>BUT!! </bold>Choosing to <bold class = 'bolded'>defect (betray)</bold> will reduce it to 2 years instead. Therefore, the best move (assuming your friend will defect) is to defect (betray) them. </p>
  
      {/if}
  
      {#if (index === 11) && (!click_cooperate2) && (click_defect2)}
      <img src={'outcome_given_defect.svg'} alt={`Slide ${index + 1}`} class="slide-image12-2">

        <h3 class='great_job'>Great Job!</h3>
        <p class="text14">
          Since <bold class = 'bolded'>betraying (defect)</bold> will reduce the sentence from 3 to 2 years, it’s reasonable why you choose to defect!
        </p >  
  
      {/if}
  
      {#if index === 12}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image15">
      <p class="text15-1"> <bold class = 'bolded'>The best move regardless of your friend’s actions is to defect (betray) them. </bold>
        
        </p >
      {/if}

      {#if index === 13}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image15">
      <p class="text15-2"> 
        If your friend also prioritizes their individual interest, 
        they will <bold class = 'bolded'> also betray (defect)</bold> you. This will lead to each of you spending <bold class = 'bolded'>2 years in prison</bold> (4 years in total). 
        </p >
      {/if}
  
      {#if index === 14}
      <img src={slides[index]} alt={`Slide ${index + 1}`} class="slide-image16">
      <h3 class="however"> However, is this the best solution?? </h3>
      <p class="text16">
        You will notice that if <bold class = 'bolded'>both of you stay silent (cooperate)</bold> for mutual benefits, each of you will only spend <bold class = 'bolded'>1 year in prison!!</bold>
      </p >
  
      {/if}

      {#if index === 15}
      <h3 class = 'text_definition'>💡 Prisoner's Dilemma: a situation in which two people have competing incentives that instead lead them to choose a suboptimal outcome</h3>
      {/if}
  
      {#if index === 16}
      <img src={slides[index-1]} alt={`Slide ${index + 1}`} class="slide-image17">
      <h3 class = 'however'>Let’s do another example to show your understanding! </h3>
      <br>
      <br>
      <p class = 'text17-2'><bold class = 'bolded'>🎸Concert time!</bold> A mutual 
        acquaintance texts each of you separately saying that she has one extra ticket 🎫 to the Eras Tour
         and asks you to join. The show is sold out and there is no way to get another ticket for your bestie.
        </p >
  
        <p class = 'text17-3'> What will you do, if each of you are making decisions <bold class = 'bolded'>on your own without telling each other the opportunity</bold>?
        </p >
      {/if}
  
      {#if index === 17}
      <img src={slides[index-1]} alt={`Slide ${index + 1}`} class="slide-image18">
      <p class = 'text18'> If <bold class = 'bolded'> you decide to go </bold> while <bold class = 'bolded'>your friend gives up the ticket</bold>, you will be happy with a happiness value of 3, but your friend will stay at home with a happiness value of 0.
      </p >
  
      {/if}
  
      {#if index === 18}
      <img src={slides[index-1]} alt={`Slide ${index + 1}`} class="slide-image19">
      <p class = 'text19'> If <bold class = 'bolded'> your friend decides to go</bold> while <bold class = 'bolded'> you give up the ticket</bold>, your friend will be happy with a happiness value of 3, but you will stay at home with a happiness value of 0.
      </p >
  
      {/if}
  
      {#if index === 19}
      <img src={slides[index-1]} alt={`Slide ${index + 1}`} class="slide-image20">
      <p class = 'text20'> If you <bold class = 'bolded'>both decide to go</bold>, you may argue about who gets the ticket, but both of you have the hope to get it, so you both have a happiness value of 1.
      </p >
  
      {/if}
  
      {#if index === 20}
      <img src={slides[index-1]} alt={`Slide ${index + 1}`} class="slide-image21">
      <p class = 'text21'> However, if you <bold class = 'bolded'>both decide to stay home</bold> and give up the ticket, you two will be both happy with a happiness value of 2, 
        slightly lower than going to the concert, but higher than arguing about the ticket.
      </p >
      {/if}
      
      {#if index === 21 && (!click_cooperate3) && (!click_defect3)}
      <img src={'practice.svg'} alt={`Slide ${index + 1}`} class="slide-image22">
      <p class = 'text22-1'> Like usual, we’ll present the outcomes in a matrix.</p >
      <p class = 'text22-2'> What will you do?</p >
      {/if}
  
  
      {#if index === 21 && ((click_cooperate3) || (click_defect3))}
      <img src={'practice_summary.svg'} alt={`Slide ${index + 1}`} class="slide-image23">
      <p class = 'text23'>
        <bold class='bolded'>The best move regardless of your friend’s actions is to go</bold>. If your friend also acts rationally, and also prioritizes their individual interest, they will also go. This will lead to each of you arguing about who gets the ticket, each with a happiness value of 1. 
      </p >
      
      {/if}
  
  
      {#if index === 22}
      <img src={slides[index-1]} alt={`Slide ${index + 1}`} class="slide-image24">
      <p class = 'text24'> However, if you <bold class='bolded'>both decide to stay home</bold> and give up the ticket, you two will be both happy with a happiness value of 2, 
        slightly lower than going to the concert, but higher than arguing about the ticket.
      </p >
      {/if}

      {#if index === 23}
      <img src={slides[index-1]} alt={`Slide ${index + 1}`} class="slide-image25">
      <p class = 'text25-0'> <bold class='bolded'>In Summary...</bold>
      </p >
      <p class = 'text25-1'> 💡 In summary, considering if there’s no communication between you and the other, 
        cooperative behavior transforms many prisoner's dilemmas toward the collectively beneficial outcome. 
      </p >
      <p class = 'text25-2'>💡 In addition to that, <bold class='bolded'>communication produces a better outcome for both of you and breaks the dilemma.</bold>
      </p>
      {/if}


    <section> 
    </section>
    <section> 
    </section>
    <section> 
    </section>
    <section> 
    </section>
    <section> 
    </section>
    <section> 
    </section>
    <section> 
    </section>
    <section> 
    </section>
    <section> 
    </section>
    <section> 
      <svg id = "section10" class = "clicker1" width="400" height="500" xmlns="http://www.w3.org/2000/svg">
      </svg>
    </section>
    <section> 
    </section>
    <section> 
      <svg id = "section12" class = "clicker2" width="400" height="500" display = 'none' xmlns="http://www.w3.org/2000/svg">
      </svg>
    </section>
    <section> 
    </section>
    <section> 
    </section>
    <section>
    </section>
    <section> 
    </section>

    <section> 
    </section>

    <section> 
    </section>

    <section> 
    </section>

    <section> 
      <svg id = "section20" class = "clicker3" width="400" height="500" display = 'none' xmlns="http://www.w3.org/2000/svg">
      </svg>
    </section>

    <section> 
    </section>

    <section> 
    </section>

    <section> 
    </section>

    <section> 
    </section>
    <section> 
    </section>

  </div>
    </div>
</Scroller>

<script>
  import Scroller from "@sveltejs/svelte-scroller";
  import { select, selectAll } from 'd3-selection';
  import { lockscroll } from '@svelte-put/lockscroll';

  // import { onMount } from 'svelte';
  import * as d3 from 'd3';
  export let slides = [];
  let index, offset;
  let click_cooperate1 = false;
  let click_cooperate2 = false;
  let click_cooperate3 = false;
  let click_defect1 = false;
  let click_defect2 = false;
  let click_defect3 = false;


  import { onMount, onDestroy } from 'svelte';
  import { writable } from 'svelte/store';

  // let locked = false;
  // function toggleLockScroll() {
  //   locked = !locked;
  // }
  function unlockScroll() {
    locked = false; // Ensure this changes a store or triggers a reactive update
  }


  let disabledScroll = false;

  let already_displayed10 = false;
  let already_displayed12 = false;
  let already_displayed20 = false;


  var button10_1;
  var button10_2;

  var button12_1;
  var button12_2;

  var button20_1;
  var button20_2;


  // lock only when any button hasn't been clicked
  $: {
      if ((index === 10) || (index === 12) || (index ===20)) {
        console.log('click_cooperate1', click_cooperate1)
        console.log('click_defect1',click_defect1)
        console.log('click_cooperate2', click_cooperate2)
        console.log('click_defect2',click_defect2)
        console.log('click_cooperate3', click_cooperate3)
        console.log('click_defect3',click_defect3)
      }
  }

  $: locked = ((index === 10) && (!click_cooperate1 && !click_defect1) 
                  || (index === 11 && (!click_cooperate2 && !click_defect2))
                  || (index === 21 && (!click_cooperate3 && !click_defect3)));

  // $: locked = ((index === 10) && (!already_displayed10) 
  //                 || (index === 11 && (!already_displayed12))
  //                 || (index === 20 && (!already_displayed20)));
                  
  

  $: {     
    if (index === 10) {
      already_displayed10 = true;
      // if index == 10, either button has been clicked already, make the buttons disappear
      // when the content changes because of click action
      if (click_cooperate1 || click_defect1) { 
        // console.log('should be gone')
        button10_1.attr('display', 'none')
        button10_2.attr('display', 'none')
        console.log(click_cooperate1, click_defect1)
      } else {
        // if index == 10 but no button has been clicked yet, that means the buttons aren't there
        // create the buttons, and lock the slide
        createClickers('#section10', 'red');
      }
    } else if (already_displayed10 === true) { // make the button disappear when scrolling backwards
        button10_1.attr('display', 'none')
        button10_2.attr('display', 'none')   
      } 
    
    if (index === 11) {
      already_displayed12 = true;
      // if index == 11, either button has been clicked already, make the buttons disappear
      // when the content changes because of click action
      if (click_cooperate2 || click_defect2) {
        // console.log('should be gone')
        console.log(click_cooperate2, click_defect2)
        button12_1.attr('display', 'none')
        button12_2.attr('display', 'none')  
      } else {
        // if index == 10 but no button has been clicked yet, that means the buttons aren't there
        // create the buttons, and lock the slide
        createClickers('#section12', 'red');
      }
     } else if (already_displayed12 === true) { // make the button disappear when scrolling backwards
        button12_1.attr('display', 'none')
        button12_2.attr('display', 'none')
      }

      if (index === 21) {
      already_displayed20 = true;
      // if index == 11, either button has been clicked already, make the buttons disappear
      // when the content changes because of click action
      if (click_cooperate3 || click_defect3) {
        // console.log('should be gone')
        button20_1.attr('display', 'none')
        button20_2.attr('display', 'none')  
      } else {
        // if index == 10 but no button has been clicked yet, that means the buttons aren't there
        // create the buttons, and lock the slide
        createClickers('#section20', 'red');
      }
     } else if (already_displayed20 === true) { // make the button disappear when scrolling backwards
        button20_1.attr('display', 'none')
        button20_2.attr('display', 'none')
      }
    }


  function createClickers(id, color) {

      const svg10_1 = d3.select('#section10');
      const svg10_2 = d3.select('#section10');

      const svg12_1 = d3.select('#section12');
      const svg12_2 = d3.select('#section12');
      // var originalStyle;

      const svg20_1 = d3.select('#section20');
      const svg20_2 = d3.select('#section20');


      if (id === '#section10') {
      button10_1 = svg10_1
        .append('rect')
        // .attr('display', 'none')
        .attr('x', 83) // X position
        .attr('y', 59)  // Y position
        .attr('width', 130) // Width
        .attr('height', 130) // Height
        .attr('fill', color) // Fill color
        .attr('opacity', 0.2)
        // .attr('box-shadow',  translate('5px 5px 10px 2px'))

        .attr('cursor', 'pointer') // Change cursor on hover
        .on('mouseover', function(event, d) {
          d3.select(this).attr('opacity', 0.4)
        })
        .on('mouseout', function() {
          d3.select(this).attr('opacity', 0.2);
        });

        button10_2 = svg10_2
            .append('rect')
            // .attr('display', 'none')
            .attr('x', 83) // Adjust these attributes as necessary
            .attr('y', 189)
            .attr('width', 130)
            .attr('height', 118)
            .attr('fill', color) // Making it red for visibility
            .attr('opacity', 0.2)
            .attr('cursor', 'pointer')
            .on('mouseover', function(event, d) {
          d3.select(this).attr('opacity', 0.4)
        })
        .on('mouseout', function() {
          d3.select(this).attr('opacity', 0.2);
        });


      // Add a click event listener to the rectangle
      button10_1.on('click', function() {
          // alert('Rectangle button clicked!');
          unlockScroll();
          click_cooperate1 = true;
      });
      button10_2.on('click', function() {
          // alert('Rectangle button clicked!');
          unlockScroll();
          click_defect1 = true;
      });
    } 
    
    else if (id === '#section12') {

      svg12_1.attr('display', 'auto');
      svg12_2.attr('display', 'auto');
      
      button12_1 = svg12_1
        .append('rect')
        // .attr('display', 'none')
        .attr('x', 83) // X position
        .attr('y', 59)  // Y position
        .attr('width', 130) // Width
        .attr('height', 130) // Height
        .attr('fill', color) // Fill color
        .attr('opacity', 0.2)
        .attr('cursor', 'pointer') // Change cursor on hover
        // .on('click', function(event) {
        //   console.log('clicked');
        // })
        .on('mouseover', function(event, d) {
          d3.select(this).attr('opacity', 0.4)
        })
        .on('mouseout', function() {
          d3.select(this).attr('opacity', 0.2);
        });

        button12_2 = svg12_2
            .append('rect')
            // .attr('display', 'none')
            .attr('x', 83) // Adjust these attributes as necessary
            .attr('y', 189)
            .attr('width', 130)
            .attr('height', 122)
            .attr('fill', color) // Making it red for visibility
            .attr('opacity', 0.2)
            .attr('cursor', 'pointer')
            .on('mouseover', function(event, d) {
          d3.select(this).attr('opacity', 0.4)
        })
        .on('mouseout', function() {
          d3.select(this).attr('opacity', 0.2);
        });


      // Add a click event listener to the rectangle
      button12_1.on('click', function() {
          console.log('clicked')
          unlockScroll();
          click_cooperate2 = true;
      });

      button12_2.on('click', function() {
          console.log('clicked')
          unlockScroll();
          click_defect2 = true;
      });
    }

    else if (id === '#section20') {

      svg20_1.attr('display', 'auto');
      svg20_2.attr('display', 'auto');

      button20_1 = svg20_1
        .append('rect')
        // .attr('display', 'none')
        .attr('x', 86) // X position
        .attr('y', 44)  // Y position
        .attr('width', 116) // Width
        .attr('height', 115) // Height
        .attr('fill', color) // Fill color
        .attr('opacity', 0.2)
        .attr('cursor', 'pointer') // Change cursor on hover
        // .on('click', function(event) {
        //   console.log('clicked');
        // })
        .on('mouseover', function(event, d) {
          d3.select(this).attr('opacity', 0.4)
        })
        .on('mouseout', function() {
          d3.select(this).attr('opacity', 0.2);
        });

        button20_2 = svg20_2
            .append('rect')
            // .attr('display', 'none')
            .attr('x', 86) // Adjust these attributes as necessary
            .attr('y', 116+44)
            .attr('width', 116)
            .attr('height', 103)
            .attr('fill', color) // Making it red for visibility
            .attr('opacity', 0.2)
            .attr('cursor', 'pointer')
            .on('mouseover', function(event, d) {
          d3.select(this).attr('opacity', 0.4)
        })
        .on('mouseout', function() {
          d3.select(this).attr('opacity', 0.2);
        });


      // Add a click event listener to the rectangle
      button20_1.on('click', function() {
          console.log('clicked')
          unlockScroll();
          click_cooperate3 = true;
      });

      button20_2.on('click', function() {
          console.log('clicked')
          unlockScroll();
          click_defect3 = true;
      });
      }
        }

</script>
  
  
  <style>
   .index {
    position:fixed;
   }


   .h3{
      position:fixed;
      text-align: center;
      display:block;
      /* font-family: "Rye", serif;
      font-weight: 400; */
      font-style: normal;
      font-size: 40px;
      max-height: 90vh;

      width: 100%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -600%);

    }
   .topic{
      position:fixed;
      text-align: center;
      display:block;
      font-family: "Rye", serif;
      font-weight: 400;
      font-style: normal;
      font-size: 40px;
      max-height: 90vh;

      width: 100%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -600%);

    } 
    
    .text1-1 {
      position: fixed;
      text-align: center;
      max-height: 90vh;
      font-size: 30px;
      /* transform: translate(150px, 150px); */
      width: 80%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -180%);
    }

    .text1-2 {
      text-align: center;
      position: fixed;
      /* max-height: 90vh; */
      font-size: 30px;
      /* transform: translate(20px, 250px); */
      /* max-width: 80%; */
      width: 80%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -10%);
    }

    .text2 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -300%);
    }

    .text3 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -400%); /* changed from -200% to -400% */
    }

    .text4 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -400%); /* for double-line text */
    }

    .text5 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -700%); /* for single-line text*/
    }

    .text6 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -400%);
    }

    .text7 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 45px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -630%); /* for 'let's summarize...' */
    }

    .text8 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -900%); /* for single-line text*/
    }

    .text9 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -450%);
    }

    .text10 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -900%);
    }

    .text11 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -900%);
    }

    .text12 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -730%);
    }

    .text12-1 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -900%);
    }

    .text12-2 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -350%);
    }

    /* .text13 {
      position: fixed;
      text-align: center;
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -500%);
    } */

    .text14 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -360%);
    }
    .text15-1 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -900%);
    }

    .text15-2 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -450%);
    }

    .however {
      position:fixed;
      text-align: center;
      display:block;
      /* font-family: "Rye", serif;
      font-weight: 400; */
      font-style: normal;
      font-size: 40px;
      max-height: 90vh;

      width: 100%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -750%);
    }

    .text16 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -400%);
    }
    .text_definition {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 60px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -100%);
      /* background-color: blue; */
    }


    .text17-1 {
      position: fixed;
      text-align: center;
      max-height: 90vh;
      font-size: 30px;
      width: 90%;
      top: 10%;
      left: 50%;
      transform: translate(-50%, -70%);
    }

    .text17-2 {
      position: fixed;
      text-align: center;
      max-height: 90vh;
      font-size: 30px;
      width: 90%;
      top: 10%;
      left: 50%;
      transform: translate(-50%, 10%);
    }

    .text17-3 {
      position: fixed;
      text-align: center;
      max-height: 90vh;
      font-size: 30px;
      width: 90%;
      top: 10%;
      left: 50%;
      transform: translate(-50%, 200%);
    }

    .text18 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -300%); /* changed from -200% to -400% */
    }
    .text19 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -300%); /* changed from -200% to -400% */
    }

    .text20 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -300%); /* changed from -200% to -400% */
    }

    .text21 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -300%); /* changed from -200% to -400% */
    }

    .text22-1 {
      position: fixed;
      text-align: center;
      max-height: 90vh;
      font-size: 30px;
      width: 90%;
      top: 10%;
      left: 50%;
      transform: translate(-50%, -150%);
    }

    .text22-2 {
      position: fixed;
      text-align: center;
      font-weight: bold;
      max-height: 90vh;
      font-size: 30px;
      width: 90%;
      top: 10%;
      left: 50%;
      transform: translate(-50%, -20%);
    }

    .text23 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -320%); /* changed from -200% to -400% */
    }

    .text24 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -450%); /* changed from -200% to -400% */
    }
    
    .text25-0 {
      position:fixed;
      text-align: center;
      display:block;
      /* font-family: "Rye", serif;
      font-weight: 400; */
      font-style: normal;
      font-size: 50px;
      max-height: 90vh;

      width: 100%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -600%);

      /* position: fixed;
      text-align: center;
      max-height: 90vh;
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -300%); */
    }

    .text25-1 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -300%); /* changed from -200% to -400% */
    }

    .text25-2 {
      position: fixed;
      text-align: center;
      /* max-height: 90vh; */
      font-size: 30px;
      width: 90%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -160%); /* changed from -200% to -400% */
    }

    .slide-image1 {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -15%) scale(40%);
      max-width: 90%;
      max-height: 90vh;
    }

    .great_job {
      position:fixed;
      text-align: center;
      display:block;
      /* font-family: "Rye", serif;
      font-weight: 400; */
      font-style: normal;
      font-size: 40px;
      max-height: 90vh;

      width: 100%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -700%);
    }

    .slide-image2 {
      position: fixed;
      width: 80%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -30%) scale(70%);
    }

    .slide-image3 {
      position: fixed;
      width: 80%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -30%) scale(70%);
    }

    .slide-image4 {
      position: fixed;
      width: 80%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -30%) scale(70%);
    }

    .slide-image5 {
      position: fixed;
      width: 80%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -30%) scale(70%);
    }

    .slide-image6 {
      position: fixed;
      width: 80%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -30%) scale(70%);
    }

    .slide-image7 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -40%) scale(40%);
    }

    .slide-image8 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -40%) scale(40%);
    }

    .slide-image9 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%;
      left: 50%;
      transform: translate(-50%, -40%) scale(40%);
    }

    .slide-image10 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -40%) scale(40%);
    }
    .slide-image11 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -40%) scale(40%);
    }

    .slide-image12 {
      position: fixed;
      width: 80%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -30%) scale(80%);
    }

    .slide-image12-2 {
      position: fixed;
      width: 80%;
      top: 40%;
      left: 50%;
      transform: translate(-50%, -30%) scale(80%);
    }

    .slide-image13 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -40%) scale(40%);
    }


    .slide-image15 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -40%) scale(37%);
    }

    .slide-image16 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -40%) scale(37%);
    }

    .slide-image17 {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -30%) scale(40%);
      max-width: 90%;
      max-height: 90vh;
    }

    .slide-image18 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -30%) scale(42%);
    }

    .slide-image19 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -30%) scale(42%);
    }

    .slide-image20 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -30%) scale(42%);
    }

    .slide-image21 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -30%) scale(42%);
    }

    .slide-image22 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -40%) scale(37%);
    }

    .slide-image23 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -40%) scale(37%);
    }

    .slide-image24 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -40%) scale(37%);
    }

    .slide-image25 {
      position: fixed;
      width: 100%; /* changed from 80% t0 95% to make the matrix bigger */
      top: 40%; /* shift up by changing 50% to 40% */
      left: 50%;
      transform: translate(-50%, -10%) scale(42%);
    }

 [slot="background"] {
  position: fixed;
  pointer-events: auto;
  background-color: rgba(0, 0, 0, 0);
  border-top: 2px solid #ff400000;
  border-bottom: 2px solid #ff400000;
  font-size: 1.4em;
  /* overflow: hidden; */
  padding: 1em;
  transform: scale(0.7) translate(-20%, -30%);
 }
 
 [slot="foreground"] {
  pointer-events: auto;
  text-align: center;
 }
 
 section {
  pointer-events: fill;
  height: 80vh;
  background-color: rgba(0, 0, 0, 0);
  color: rgb(7, 0, 0);
  padding: 1em;
 }


  .bolded {
    font-weight: bold;
  }

  .clicker1 {
    pointer-events: auto;
    position: fixed;
    top:50%;
    left:50%;
    transform: translate(-53%, 2%);
    z-index: 100;
    /* display: block */
 }

 .clicker2 {
    pointer-events: auto;
    position: fixed;
    top:50%;
    left:50%;
    transform: translate(-53%, 2%);
    z-index: 100;
    /* display: block */
 }

 .clicker3 {
    pointer-events: auto;
    position: fixed;
    top:50%;
    left:50%;
    transform: translate(-53%, 2%);
    z-index: 100;
    /* display: block */

}


  </style>
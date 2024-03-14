<script>
  import ScrollyTeller from '../components/ScrollyTeller.svelte';

  // Your slides array, containing paths to images or SVG content
  const slides = [
    'first_page.svg', //0
    'no_talking.svg', //1
    'defect-silent.svg', //2
    'silent-defect.svg', //3
    'defect-defect.svg', //4
    'silent-silent.svg', //5

    'matrix_start.svg', //6
    'matrix_silent.svg', //7
    'matrix_mix.svg', //8
    'matrix_defect.svg', //9
    'interact_given_cooperate.svg', //10

    'interact_given_defect.svg', //11

    'summary_matrix.svg', //12
    'summary_matrix.svg', //13

    'summary_matrix.svg', //14

    'example_first_page.svg', //15
    'happy_sad.svg', //16
    'sad_happy.svg', //17
    'happy_happy.svg', //18
    'sad_sad.svg', //19
    
    'practice.svg', //20
    // 'practice_summary.svg', // appears twice; // 21
    'practice_summary.svg', //22
    'summary_summary.svg' //23
  ];
</script>

<ScrollyTeller {slides} />

<style>
  /* Additional styling as needed */
</style>
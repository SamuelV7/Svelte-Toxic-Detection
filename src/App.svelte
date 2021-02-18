<script>
  import ToxicityDetector from './ToxicityDetector.svelte'
  export let name = "Toxicity Detection";
  import {
    MDBBtn,
    MDBCard,
    MDBCardBody,
    MDBCardImage,
    MDBCardTitle,
    MDBCardText,
    MDBCol,
    MDBContainer,
  } from "mdbsvelte";
//import ToxicModel from './ToxicModel.svelte';
</script>


<main>
  <h1>{name}!</h1>
  <p>Detect Toxicity of the sentence!</p>
  <!-- <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p> -->
</main>

<!-- <MDBContainer>
	<MDBBtn>Click Me</MDBBtn>
</MDBContainer> -->

<MDBCol>
  <MDBCard color="">
    <MDBCardBody>
      <MDBContainer>
		  <ToxicityDetector/>
      </MDBContainer>
    </MDBCardBody>
  </MDBCard>
</MDBCol>

<style>
	/* #test{
		  margin: auto;
		  color: aliceblue;
		  align-self: center;
	  } */

	main {
	  text-align: center;
	  padding: 1em;
	  max-width: 240px;
	  margin: 0 auto;
	}
  
	h1 {
	  color: #393e46;
	  text-transform: uppercase;
	  font-size: 4em;
	  font-weight: 100;
	}
  
	@media (min-width: 640px) {
	  main {
		max-width: none;
	  }
	}
  </style>
  

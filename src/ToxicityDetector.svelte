<script>
  import { MDBContainer, MDBRow, MDBCol, MDBBtn } from "mdbsvelte";
  import "@tensorflow/tfjs";
  import * as toxicity from "@tensorflow-models/toxicity";

  let userSentence = "";
  const threshold = 0.85;

  async function modelPrediction() {
    console.log(userSentence);
    let inputSentence = [userSentence];
    const model = await toxicity.load(threshold);
    const prediction = await model.classify(inputSentence);
    console.log(prediction);
    return prediction;
  }
  let promise = Promise.resolve();
  function handleClick() {
    promise = modelPrediction();
    return promise;
  }
</script>

<style>
  ul {
    color: #00adb5;
  }
</style>

<div>
<textarea bind:value={userSentence} class="textArea" cols="75" />
<button on:click={handleClick}>Click To Classify</button>
{#await promise}
  <p>Waiting.....</p>
{:then model1}
  {console.log(model1)}
  {#if model1 != undefined}
  <div>
    <ul>Identity Attack: {model1[0].results[0].match}</ul>
    <ul>Insult: {model1[1].results[0].match}</ul>
    <ul>Obscene: {model1[2].results[0].match}</ul>
    <ul>Severe Toxicity: {model1[3].results[0].match}</ul>
    <ul>Sexually Explicit: {model1[4].results[0].match}</ul>
    <ul>Threat: {model1[5].results[0].match}</ul>
    <ul>Toxicity: {model1[6].results[0].match}</ul>
  </div>
  {/if}
{:catch error}
  console.log(error)
{/await}
</div>

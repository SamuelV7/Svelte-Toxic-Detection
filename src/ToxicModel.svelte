<script>
 import "@tensorflow/tfjs";
 import * as toxicity from "@tensorflow-models/toxicity";


//  async function getPrediction(sentence) {
//   const threshold = 0.9;
//   let theSentence = [sentence];
//   const model = await toxicity.load(threshold);
//   const prediction = await model.classify(theSentence);
//   return prediction;
// }

// async function cleanMlOutput(sentence) {
//   let mlPrediction = await getPrediction(sentence);
//   let mlObjectArray;

//   for (let i = 0; i < mlPrediction.length; i++) {
//     let modelObject;
//     modelObject.label = mlPrediction[i].label;
//     modelObject.resultMatch = mlPrediction[i].results[0].match;
//     modelObject.resultProbablity.push(mlPrediction[i].results[0].probabilities);
//     console.log(modelObject);
//     mlObjectArray.push(modelObject);
//   }
//   return mlObjectArray;
// }

let getModelOut = async (sentence)=>{
  const threshold = 0.9
  let inputSentence = [sentence]
  const model = await toxicity.load(threshold)
}
export getModelOut
</script>

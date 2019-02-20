### brain.js
---
https://github.com/BrainJS/brain.js

```js
const config = {
  binaryThresh: 0.5,
  hiddenLayers: [3],
  activation: 'sigmoid',
  leakyReluAlpha: 0.01
};

const net = new brain.NeuralNetwork(config);

net.train([{input: [0, 0], output: [0]},
  {input: [0, 1], output: [1]},
  {input: [1, 0], output: [1]}, 
  {input: [1, 1], output: [0]}]);

const output = net.run([1, 0]);


const config = {
  inputSize: 20,
  inputRange: 20,
  hiddenLayers: [20,20],
  outputSize: 20,
  learningRate: 0.01,
  decayRate: 0.999,
};

const net = new brain.recurrent.RUN(config);

net.train([{input: [0, 0], output: [0]},
  {input: [0, 1], output: [1]},
  {input: [1, 0], output: [1]},
  {input: [1, 1], output: [0]}]);

const output = net.run([0, 0]);
output = net.run([0, 1]);
output = net.run([1, 0]);
output = net.run([1, 1]);


const net = new brain.NeuralNetwork();

net.train([{input: { r: 0.03, g: 0.7, b: 0.5 }, output: { black: 1 },
  {input: { r: 0.16, g: 0.09, b: 0.2 }, output: { white: 1 }},
  {input: { r: 0.5, g: 0.5, b: 1.0 }, output: { white: 1 }}}]);

const output = net.run({ r: 1, g: 0.4, b: 0 });


const net = new brain.recurrent.LSTMTimeStep();

net.train([
  [1,2,3]
]);

const output = net.run([1, 2]);


const net = new brain.recurrent.LSTMTimeStep([
  inputSize: 2,
  hiddenLayers: [10],
  outputSize: 2
]);

net.train([
  [1, 3],
  [2, 2],
  [3, 1]
]);

const output = net.run([[1, 3], [2, 2]]);


const net = new brain.recurrent.LSTM();

net.train([
  'doe, a deer, a female deer',
  'ray, a drop of golden sun', 
  'me, a name I call myself'
]);


const net = new brain.recurrent.LSTM();

net.train([
  { input: 'I feel great about the world!', output: 'happy' },
  { input: 'The world is a terrible place!', output: 'sad' }
]);

const output = net.run('I feel great about the world');

net.train(data, {
  iteration: 20000,
  errorThresh: 0.005,
  log: false,
  logPeriod: 10,
  learningRate: 0.3,
  momentum: 0.1,
  callback: null,
  callbackPeriod: 10,
  timeout: Infinity
});


const net = new brain.NeuralNetwork();
const net2 = new brain.NeuralNetwork();

const p1 = net.trainAsync(data, options);
const p2 = net.trainAsync(data, options);

Promise
  .all([p1, p2])
  .then(values => {
    const res = value[0];
    const res2 = values[1];
    console.log(`net trained in ${ res.iterations} and net2 trained in ${res2.iterations}`);
  })
  .catch(handleError);


const crossValidate = new brain.CrossValidate(brain.NeuralNetwork, networkOptions);
crossValidate.train(data, trainingOptions, k);
const json = crossValidate.toJSON();
const net = crossValidate.toNeuralNetwork();

const json = crossValidate.toJSON();
const net = crossValidate.fromJSON(json);


const net = new brain.NeuralNetwork();
const trainStream = new brain.TrainStream({
  neuralNetwork: net,
  floodCallback: function(){
    flood(tainStream, data);
  },
  doneTrainingCallback: function(stats) {
  }
});

readInputs(trainStream, data);

function readInputs(stream, data) {
  for(let i = 0; i < data.length; i++) {
    stream.write(data[i]);
  }
  
  stream.endInputs();
}


const net = new brain.NeuralNetwork();
net.fromJSON(json);
net.run(input);

const net = new brain.LSTMTimeStep();
net.fromJSON(json);
net.run(input);

const net = new brain.LSTMimeStep();
net.fromJSON(json);
net.run(input);


const net = new brain.LSTMTimeStep();
net.fromJSON(json);
net.forecast(input, 3);


const net = new brain.recurrent.LSTM();

net.maxPredictionLength = 100000000;
net.run(`Once upon a time`);

const json = net.toJSON();
net.fromJSON(json);

const run = net.toFunction();
const output = run({ r: 1, g: 0.4, b: 0 });
console.log(run.toString());

const net = new brain.NeuralNetwork({
  activation: 'sigmoid',
  hiddenLayers: [4],
  leaningRate: 0.6
});


hiddenLayers: [3, 4]

const likely = require('brain/likely');
const key = likely(input, net);


document.getElementById('result').innerHTML = brain.utilities.toSVG(network,options)
```

```
npm install brain.js
yarn add brain.js

```

```
{
  error: 0.0039138888888888888,
  iterations: 406
}
```



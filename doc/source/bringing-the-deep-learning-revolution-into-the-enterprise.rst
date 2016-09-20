=========================================================
Bringing the Deep Learning Revolution into the Enterprise
=========================================================

*Speaker: Michael Gschwind*

* Collecting data is useful but you must make sense out of it, especially in
  real-time
* Deep Learning is at the intersection of AI + machine learning + big data
* What is deep learning?

  * Things you do without thinking about it -- like recognizing a bicycle
  * Bicycles come in many forms and it's difficult to teach a computer how to
    recognize them
  * Humans can deal with complexity/variance easily, but traditional
    recognition technology cannot
  * Deep learning involves building a model based on patterns, and then allow
    you to take an action on that (and predict outcomes)

* Applications

  * Automotive/transportation: driverless cars
  * Security/Safety: facial/object recognition
  * Consumer web/mobile/retail: natural language processing, recommendations
  * Medicine/biology: diagnostic assistance and drug discovery
  * Broadcast/media: Captioning, recommendations

* Computing capacity has been a big limiter in deep learning, but accelerators
  are helping
* Based on artificial neural networks (ANNs)

  * Inspired by biological neural networks in the brain
  * A neuron is a basic cognitive unit and you need a lot of them to begin
    making decisions
  * Expressed in computers as multiple layers, nodes, weights and activation
    functions (what to do when a threshold is crossed)
  * Recognizing something takes multiple steps in animals and in computers

* Training a neural network

  * Called stochastic gradient descent (SGD)
  * Shows how well a trained network is
  * Involves taking a lot of derivatives to find "valleys"

* Middleware exists to help with the mathematics and training of a neural
  network, such as Caffe, TensorFlow, CNTK, and torch
* Two-tiered workload

  * Training: extract a model from historical data
  * Inference: classify new objects based on the model

* Computers will return results with a probability attached
* More training improves the probability of being right
* Pre-packaged for POWER systems: http://ibm.biz/power-mldl


Large Language Models are a subset of [[Deep Learning]]

![[Excalidraw/Drawing 2023-09-29 15.36.56.excalidraw]]

Also intersects w/ Generative Learning


What is LLM?
	Large, general-purpose language models can be pre0trained and then fine-tuned for specific purposes

- Large
	- Large training dataset
	- Large number of parameters
- General Purpose
	- commonality of human languages
	- Resource restriction
- Pre-trained and fine-tuned


Benefits of using LLM
- A single model can be used for different tasks
- Fine-tune process requires minimal field data
- The performance is continuously growing w/ more data and parameters


![](Meta/Pasted%20image%2020230929154843.png)

- Prompt Design
	- Prompts involve instructions and context passed to a language model to achieve a desired task
	- specific task
	- general
- Prompt Engineering
	- Prompt engineering is the practice of developing and optimizing prompts to efficiently use language models for a variety of applications
	- specialize

3 kinds of LLM
1. Generic (or Raw) Language Models - Predict the next word (technically token) based on the language in the training data.
2. Instruction Tuned - Trained to predict a response to the instructions given in the input
3. Dialog Tuned - Trained to have a dialog by predicting the next response.


Tuning is the process of adapting a model to a new domain or set of custom use cases by training the model on new data.  ie setting the model to specifically for legal or medical domain.

Fine Tuning - Bring your own dataset of and retrain the model by tuning every weight in the LLM. This requires a big training job (really big) and hosting your own fine-tuned model.
	-This is very expensive

More efficient methods of tuning
- Parameter-Efficient Tuning Methods (PETM)
	- Method for tuning an LLM on your own custom data w/out duplicating the model. The base model itself is not altered. Instead, a small number of add-on layers are tuned, which can be swapped in and out at inference time.
	- Prompt turning 
		- One of the easiest parameter Efficient Tuning methods


National Language Processing (NLP)
Computer Vision (CV)
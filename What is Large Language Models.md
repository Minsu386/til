
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


## Review
What are some of the challenges of using LLMs? Select three options.

Note: To get credit for a multiple-select question, you must select all of the correct options and none of the incorrect ones.

_close_After being developed, they only change when they are fed new data.

Incorrect. Please review the course again.

_check_They can be biased.

You selected a correct option!

They can be used to generate harmful content.

_check_They can be expensive to train.

You selected a correct option!

_check_

2.

What are some of the applications of LLMs?

LLMs can be used for many tasks, including:

1. Writing
2. Translating
3. Coding
4. Answering questions
5. Summarizing text
6. Generating non-creative discrete probabilities

_check_LLMs can be used for many tasks, including:

1. Writing
2. Translating
3. Coding
4. Answering questions
5. Summarizing text
6. Generating creative content

LLMs can be used for many tasks, including:

1. Writing
2. Translating
3. Coding
4. Answering questions
5. Summarizing text
6. Generating non-creative discrete predictions

LLMs can be used for many tasks, including:

1. Writing
2. Translating
3. Coding
4. Answering questions
5. Summarizing text
6. Generating non-creative discrete classes

LLMs can be used for many tasks, including:

1. Writing
2. Translating
3. Coding
4. Answering questions
5. Summarizing text
6. Generating non-creative discrete probabilities, classes, and predictions.

Correct! LLMs can be used for many tasks, including: 1. Writing 2. Translating 3. Coding 4. Answering questions 5. Summarizing text 6. Generating creative content

_check_

3.

What are some of the benefits of using large language models (LLMs)?

LLMs have a number of benefits, including:

1. They can generate human-quality text.
2. They can be used for many tasks, such as text summarization and code generation.
3. They can be trained on massive datasets of text, images, and code.
4. They are constantly improving.

LLMs have many benefits, including:

1. They can generate discrete classes and human-quality text.
2. They can be used for many tasks, such as text summarization and code generation.
3. They can be trained on massive datasets of text and code.
4. They are constantly improving.

LLMs have many benefits, including:

1. They can generate probabilities and human-quality text.
2. They can be used for many tasks, such as text summarization and code generation.
3. They can be trained on massive datasets of text and code.
4. They are constantly being improved.

_check_LLMs have many benefits, including:

1. They can generate human-quality text.
2. They can be used for a variety of tasks.
3. They can be trained on massive datasets of text and code.
4. They are constantly improved.

LLMs have a number of benefits, including:

1. They can generate non-probabilities and human-quality text.
2. They can be used for many tasks, such as text summarization and code generation.
3. They can be trained on massive datasets of text, image, and code.
4. They are constantly improving.

\Correct! LLMs have many benefits, including: \1. They can generate human-quality text. \2. They can be used for a variety of tasks. \3. They can be trained on massive datasets of text and code. \4. They are constantly improving. \

_check_

4.

What are large language models (LLMs)?:

Generative AI is a type of artificial intelligence (AI) that only can create new content, such as text, images, audio, and video by learning from new data and then using that knowledge to predict a classification output.

Generative AI is a type of artificial intelligence (AI) that can create new content, such as discrete numbers, classes, and probabilities. It does this by learning from existing data and then using that knowledge to generate new and unique outputs.

_check_An LLM is a type of artificial intelligence (AI) that can generate human-quality text. LLMs are trained on massive datasets of text and code, and they can be used for many tasks, such as writing, translating, and coding.

Generative AI is a type of artificial intelligence (AI) that only can create new content, such as text, images, audio, and video by learning from new data and then using that knowledge to predict a discrete, supervised learning output.

Correct! An LLM is a type of artificial intelligence (AI) that can generate human-quality text. LLMs are trained on massive datasets of text and code, and they can be used for a variety of tasks, such as writing, translating, and coding.
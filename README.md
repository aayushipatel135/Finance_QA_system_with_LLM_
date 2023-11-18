# Finance_QA_system_with_LLM

## Dataset Collection

### 1) MCQ collection
* data is collected from diffrent specialized educational institutions that cater to candidates preparing for the demanding CA exam. This involved a collection of approximately 1000 finely crafted multiple-choice questions (MCQs). Which covers the topics which are asked in CA exam.
* Another set of MCQs is also collected by the same way but this set of MCQs is used for RLHF training which covers around 200 MCQs.
* And for test set 50 MCQs were collected.

### 2) Explanation Generation for Collected MCQs
* In order to apply chain-of-thought prompting explanation for the correct answer is required. To generate the explanation ChatGpt was used.

### 3) Question Answer
* For question answering task <a href="https://huggingface.co/datasets/dreamerdeo/finqa">finqa</a> dataset was used.

### 4) Sentiment Classification
* For sentiment classification task  <a href="https://huggingface.co/datasets/financial_phrasebank>financial_phrasebank</a> dataset was used.

## Finetuning
* To train a Large Language model high resources are required that's why we adapted a pre-trained LLM and finetuned it with Q-LORA technique.
* Q-LORA which is similar to LORA. Instead of chaning pre-trained weights for specific domain it assigns the new set of weights and train them for specific domain. And uses the already pre-trained weights as the understanding of natural language.

<img src="https://images.ctfassets.net/xjan103pcp94/6fct47v2q8PU36X9A1TUzN/62bf8834293c1ec4a7e591f42ed1ffd1/pretrainined-weights-diagram-lora-blog.png" alt="Loading...">
<img src="https://heidloff.net/assets/img/2023/09/qlora.png" alt="Loading...">

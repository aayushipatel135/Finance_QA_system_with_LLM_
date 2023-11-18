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


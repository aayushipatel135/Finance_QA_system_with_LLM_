# Finance_QA_system_with_LLM

## Dataset Collection

#### 1) MCQ collection
* data is collected from diffrent specialized educational institutions that cater to candidates preparing for the demanding CA exam. This involved a collection of approximately 1000 finely crafted multiple-choice questions (MCQs). Which covers the topics which are asked in CA exam.
* Another set of MCQs is also collected by the same way but this set of MCQs is used for RLHF training which covers around 200 MCQs.
* And for test set 50 MCQs were collected.
* Data is collected from following
<ol>
  <li>https://edurev.in/p/88787/MCQ-on-Principles-of-Accountancy--with-answers-</li>
  <li>https://mcqmate.com/topic/777/principles-of-accounting-set-2#google_vignette</li>
  <li>https://mcqmate.com/topic/891/business-laws#google_vignette</li>
  <li>https://engineeringinterviewquestions.com/business-mathematics-mcqs-and-answers/</li>
  <li>https://gstguntur.com/ca-foundation-bck-mcq-questions/#BCK_CA_Foundation_MCQ_Questions_PDF_%7C_CA_Foundation_Business_and_Commercial_Knowledge_MCQs_PDF</li>
  <li>https://sde.uoc.ac.in/sites/default/files/sde_videos/Strategic%20Financial%20Management.pdf</li>
  <li>https://zeroinfy.in/pages/ca-final-law-chapterwise-mcqs</li>
  <li>https://icmai.in/upload/Students/mcq/Final/Paper20.pdf</li>
  <li>https://icmai.in/upload/Students/mcq/Final/PAPER-16.pdf</li>
</ol>

#### 2) Explanation Generation for Collected MCQs
* In order to apply chain-of-thought prompting explanation for the correct answer is required. To generate the explanation ChatGpt was used.

#### 3) Question Answer
* For question answering task <a href="https://huggingface.co/datasets/dreamerdeo/finqa">finqa</a> dataset was used.

#### 4) Sentiment Classification
* For sentiment classification task  <a href="https://huggingface.co/datasets/financial_phrasebank">financial_phrasebank</a> dataset was used.

## Finetuning
* To train a Large Language model high resources are required that's why we adapted a pre-trained LLM and finetuned it with Q-LORA technique.
* Q-LORA which is similar to LORA. Instead of chaning pre-trained weights for specific domain it assigns the new set of weights and train them for specific domain. And uses the already pre-trained weights as the understanding of natural language.

<p float="left">
  <img src="https://images.ctfassets.net/xjan103pcp94/6fct47v2q8PU36X9A1TUzN/62bf8834293c1ec4a7e591f42ed1ffd1/pretrainined-weights-diagram-lora-blog.png" alt="Loading..." width="33%" height="250px">
  <img src="https://heidloff.net/assets/img/2023/09/qlora.png" alt="Loading..."  width="33%" height="250px">
</p>

## RLHF Training
The initial step in Reinforcement Learning from Human Feedback (RLHF) involves creating a finance-specific reward model by fine-tuning BLoom-3b and mistral-7b models and ChatGpt. Responses are categorized based on rewards, and a domain-specific dataset was created. Reward model trained on this dataset and used as a component in Proximal Policy Optimization (PPO) to align model responses with finance-specific expectations.

  <img src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Feaa43444-8926-49a9-b44a-f8c570dc7611_826x528.png" alt="Loading..."  width="33%" height="250px">

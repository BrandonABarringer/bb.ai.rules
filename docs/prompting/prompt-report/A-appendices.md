# A Appendices

## A.1 Definitions of Prompting

Table A.1: Definitions of Prompt and Prompt Engineering from different papers.

## A.2 Extended Vocabulary

### A.2.1 Prompting Terms

**Context Window**

The context window is the space of tokens (for LLMs) which the model can process. It has a maximal length (the context length).

**Priming**

(Schulhoff, 2022) refers to giving a model an initial prompt that lays out certain instructions for the rest of a conversation. This priming prompt might contains a role or other instructions on how to interact with the user. Priming can either be done in the system or user prompt (see below).

### A.2.2 Prompt Engineering Terms

**Conversational Prompt Engineering**

is Prompt Engineering in colloquio. That is, during the course of a conversation with a GenAI, a user may ask the GenAI to refine its output. In contrast, prompt engineering is often done by sending the GenAI a completely new prompt rather than continuing a conversation.

### A.2.3 Fine-Tuning Terms

**Prompt-Based Learning**

(Liu et al., 2023b), also known as Prompt Learning (Liu et al., 2023b; Wang et al., 2023d) refers to the process of using prompting-related techniques. It often is used in the context of fine-tuning, especially fine-tuning prompts. Due to conflicting usage, we do not use this term.

**Prompt Tuning**

(Lester et al., 2021) refers to directly optimizing the weights of the prompt itself, usually through some form of gradient-based updates. It has also been referred to has Prompt Fine-Tuning.

It should not be used to refer to discrete prompt engineering.

### A.2.4 Orthogonal Prompt Types

We now discuss terminology for high-level ways of classifying prompts.

#### A.2.4.1 Originator

**User Prompt**

This is the type of prompt that comes from the user. This is the most common form of prompting and is how prompts are usually delivered in consumer applications.

**Assistant Prompt**

This "prompt" is simply the output of the LLM itself. It can be considered a prompt (or part of one) when it is fed back into the model, for example as part of a conversation history with a user.

**System Prompt**

This prompt is used to give LLMs high level instructions for interacting with users. Not all models have this.

#### A.2.4.2 Hard vs Soft Prompts

**Hard (discrete) Prompt**

These prompts only contain tokens that directly correspond to words in the LLM vocabulary.

**Soft (continuous) Prompt**

These prompts contain tokens that may not correspond to any word in the vocabulary (Lester et al., 2021; Wang et al., 2023c). Soft prompts can be used when fine-tuning is desired, but modifying the weights of the full model is prohibitively expensive. Thus, a frozen model can be used while allowing gradients to flow through the prompt tokens.

Hard Prompts ⊆ Soft Prompts

#### A.2.4.3 Prediction Styles

In LLMs, a prediction style is the format in which it predicts the next token. There are two common formats for this in prompting research. We do not discuss non-text prediction styles.

**Cloze**

In Cloze prompts, the token(s) to be predicted are presented as "slots to fill", usually somewhere in the middle of the prompt (Liu et al., 2023b). This is usually the case for earlier transformer models such as BERT (Chu and Lin, 2023).

**Prefix**

In Prefix prompts, the token to be predicted is at the end of the prompt (Liu et al., 2023b). This is usually the case with modern GPT-style models (Radford et al., 2019b).

## A.3 Datasheet

We present a datasheet (Gebru et al., 2021) with more information about the associated paper dataset, which is hosted on HuggingFace.

### A.3.1 Motivation

For what purpose was the dataset created? Was there a specific task in mind? Was there a specific gap that needed to be filled? Please provide a description.

This dataset was created to gather existing literature on prompt engineering in order to analyze all current hard prefix prompting techniques.

Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)?

This research was associated with the University of Maryland, Learn Prompting, and sponsored by OpenAI, but not created on the behalf of any particular organization.

Who funded the creation of the dataset? If there is an associated grant, please provide the name of the grantor and the grant name and number.

OpenAI contributed $10,000 in credits for their API.

### A.3.2 Composition

What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)? Are there multiple types of instances (e.g., movies, users, and ratings; people and interactions between them; nodes and edges)? Please provide a description.

The dataset contains 1,565 research papers in PDF format. Any duplicate papers were removed automatically, though some could exist.

What data does each instance consist of? "Raw" data (e.g., unprocessed text or images) or features? In either case, please provide a description.

Each data instance is a research paper as a PDF.

Is there a label or target associated with each instance? If so, please provide a description.

No

Is any information missing from individual instances? If so, please provide a description, explaining why this information is missing (e.g., because it was unavailable). This does not include intentionally removed information, but might include, e.g., redacted text.

No.

Are there any errors, sources of noise, or redundancies in the dataset? If so, please provide a description.

The papers were gathered in a semi-automated process which introduced the possibility of irrelevant papers being collected and relevant papers not being collected. There were manual reviews done for both possible errors to mitigate these errors.

Is the dataset self-contained, or does it link to or otherwise rely on external resources (e.g., websites, tweets, other datasets)?

It is self-contained.

Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by doctor–patient confidentiality, data that includes the content of individuals' non-public communications)? If so, please provide a description.

No.

Does the dataset contain data that, if viewed directly, might be offensive, insulting, threatening, or might otherwise cause anxiety? If so, please describe why.

The dataset contains some papers on prompt injection. These papers may contain offensive content including racism and sexism.

### A.3.3 Collection Process

How was the data associated with each instance acquired?

The dataset was compiled from Arxiv, Semantic Scholar, and ACL.

What mechanisms or procedures were used to collect the data?

We wrote scripts to automatically query the APIs of Arxiv and Semantic Scholar.

Over what timeframe was the data collected?

The dataset was curated the duration of the research paper, primarily in February of 2024.

Were any ethical review processes conducted?

No.

### A.3.4 Preprocessing/ Cleaning/ Labeling

Was any preprocessing/cleaning/labeling of the data done?

After collecting data from different sources, we removed duplicate papers and did a manual and semi-automated review of papers to ensure they were all relevant.

Was the "raw" data saved in addition to the preprocessed/cleaned/labeled data?

No, we do not anticipate the use of our preprocessed data. However, raw data can be recovered from the links we store.

Is the software that was used to preprocess/clean/label the data available?

It is contained within our code repository on Github.

### A.3.5 Uses

Has the dataset been used for any tasks already?

No.

Is there a repository that links to any or all papers or systems that use the dataset?

Yes.

Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses?

All of the papers we collected were written in English. It is possible some papers were not included due to a translation not being available.

Are there tasks for which the dataset should not be used?

No.

### A.3.6 Distribution

Will the dataset be distributed to third parties outside of the entity on behalf of which the dataset was created?

No.

### A.3.7 Maintenance

Who will be supporting/hosting/maintaining the dataset?

Our team will continue maintenance.

How can the owner/curator/manager of the dataset be contacted?

Please email us at sanderschulhoff@gmail.com

Is there an erratum?

No.

If others want to extend/augment/build on/contribute to the dataset, is there a mechanism for them to do so?

Yes, anyone is free to use/modify the data.

## A.4 Keywords

Here are the keywords we used for search.

• jailbreak prompt
• prompt an llm
• prompt a large language model
• prompt injection
• prompt optimization
• prompt engineering
• few-shot learning
• few shot learning
• prompt-based methods
• prompt based methods
• prompting-based methods
• prompting based methods
• few-shot prompt
• few shot prompt
• one-shot prompt
• one shot prompt
• few-shot prompting
• few shot prompting
• one-shot prompting
• one shot prompting
• prompting techniques
• prompt engineering techniques
• llm prompting
• large language model prompting
• 0-shot prompt
• 0 shot prompt
• zero-shot prompt
• many-shot prompt
• zero-shot prompting
• many-shot prompting
• in-context learning
• in context learning
• transformer model prompts
• prompt-based transfer learning
• nlp prompting strategies
• llm interpretability via prompts
• curriculum learning with prompts
• feedback loops in llm prompting
• human-in-the-loop prompting
• token-efficient prompting
• multimodal prompting
• instruction prompting
• prompt templating
• prompt template

## A.5 Prompt for Systematic Literature Review

Please find the prompt we used here. We present it in text in this document, but note that you should use the version in our codebase rather than copy and paste this.

We used the following system prompt:

You are a lab assistant, helping with a systematic review on prompt engineering. You've been asked to rate the relevance of a paper to the topic of prompt engineering. To be clear, this review will strictly cover hard prefix prompts. For clarification: Hard prompts have tokens that correspond directly to words in the vocab. For example, you could make up a new token by adding two together. This would no longer correspond to any word in the vocabulary, and would be a soft prompt Prefix prompts are prompts used for most modern transformers, where the model predicts the words after this prompt. In earlier models, such as BERT, models could predict words (e.g. <MASK>) in the middle of the prompt. Your job is to be able to tell whether a paper is related to (or simply contains) hard prefix prompting or prompt engineering.

Please note that a paper might not spell out that it is using "hard prefix" prompting and so it might just say prompting. In this case, you should still rate it as relevant to the topic of prompt engineering. Please also note, that a paper that focuses on training a model as opposed to post-training prompting techniques is considered irrelevant. Provide a response in JSON format with two fields: 'reasoning' (a single sentence that justifies your reasoning) and 'rating' (a string that is one of the following categories: 'highly relevant', 'somewhat relevant', 'neutrally relevant', 'somewhat irrelevant', 'highly irrelevant') indicating relevance to the topic of prompt engineering)

Then, we used this user prompt template to input information for each paper: Title: '{title}', Abstract: '{abstract}'. Rate its relevance to the topic of prompt engineering as one of the following categories: 'highly relevant', 'somewhat relevant', 'neutrally relevant', 'somewhat irrelevant', 'highly irrelevant', and provide text from the abstract that justifies your reasoning

## A.6 Evaluation Table

[THIS IS TABLE: A detailed evaluation table with columns for PROMPT ID, MODEL, OUTPUT SPACE, TYPE RES. BATCH, and various prompting techniques including Roles, CoT, Definition, Few-Shot. The table lists numerous research papers with their corresponding models (GPT-family, PaLM, ChatGPT, etc.) and evaluation metrics.]

Table A.2: Evaluation Paper Summary. E: Explicit (whether the model generates an assessment), I: Implicit (whether an assessment is derived from the model output); Response (Res.) S: Single response, M: Multiple responses; †: Model generated instruction;

## A.7 Entrapment Prompting Process

This section contains the thought process of our prompt engineer as he developed the prompt.

### A.7.1 Exploration

• First did a bit of dataset exploration, looking at length/label distribution, then chose entrapment to start with.
• Checked if gpt-1106-preview understood entrapment, by asking it to define the term WRT SCS. It did not.

### A.7.2 Getting a Label

• Showed it the definition of entrapment in the system prompt and asked it to label a data point, but it responded saying I should seek mental health support.
• I put the instructions in the user prompt, but get a similar response.
• Appending "Is this entrapment? Yes or no" got it to actually respond with a label.
• I gave it a reject example, but it labeled it as accept, and also sometimes gives emotional responses about getting help.
• Using 10-shot prompting, it still gives the get help responses.
• I tried removing the definition, got the same problem. It seems that it doesn't like "accept"/"reject" as labels.
• I added back the definition, changed labels to entrapment/not entrapment, it often says "not enough info to determine".
• I switched to GPT-4-32K, which gave one word responses and correctly predicted a reject and an accept datapoint.

### A.7.3 Varying Prompting Techniques

• Tested 0-shot with context.
• 10-shot with context, showed improvement.
• Taking first failing instance into playground. (12th in train file)
• Tried doing 'A: Let's go step by step and figure this out: ", output "A: Yes"
• Did "A: Let's go step by step and figure this out: ", OUTPUT: The individual in this post is expressing feelings of hopelessness, loneliness, and despair. They mention a significant loss (their mother) and a subsequent decline in their mental health, turning to alcohol as a coping mechanism. They also mention financial struggles and the possibility of becoming homeless. They express feelings of guilt and shame about their situation and compare themselves negatively to their friends and family. Most concerning is their detailed plan for suicide, involving sleeping pills and alcohol. They also mention considering stepping in front of a car. Given these factors, the label for this post would be "Yes" for expressing feelings of entrapment.
• "A: Before predicting a label, let's go step by step and write out your thought process. Use the items in the definition of entrapment to support your conclusion.", OUTPUT: Before predicting a label, let's go step by step and write out your thought process. Use the items in the definition of entrapment to support your conclusion.
• Began discussing with the AI "they don't ever say they feel trapped or that there is no way out, how did u get that idea?", OUTPUT: The individual doesn't explicitly state that they feel trapped or that there is no way out, but their narrative suggests a sense of entrapment. They mention that they are facing eviction, struggling with debt, and dealing with a decrease in income. They also express a sense of hopelessness and despair, and contemplate suicide as a potential solution to their problems. These elements suggest a feeling of being trapped in their current circumstances with no apparent way out. However, it's important to note that this interpretation is based on the information provided in the post and the individual's expressed feelings and thoughts.
• Asked it to help reformulate instructions to make explicitness more clearly needed, still predicts entrapment.
• Added "ENTRAPMENT MUST BE EXPLICIT, NOT IMPLICIT." to instruction at top after definitions (no CoT inducer)
• Also tried with previous CoT inducer, still says entrapment in a hard to parse out way.
• Added "If the person does not explicitly say they feel trapped, this doesn't count as entrapment." (no CoT), still entrapment.
• Talking to AI, it thinks "Today I found out I have 10 days to vacate my apartment or I'll be formally evicted. I'm 2 months behind on my rent due to a bad time where I got demoted at work and rent from making roughly $1000 ever 2 weeks to around $450. If I get evicted, I'll probably be homeless" is feeling trapped/stuck.
• Tried "Before stating a label, write out reasoning using the grid above about why this may/may not be entrapment:", still thinks entrapment.
• paste in email: [REDACTED] above definition of entrapment
• remove shots, says "Entrapment"
• add this after def: IMPORTANT: Only label the post as entrapment if they explicitly say that they feel trapped., says "Yes"
• In the prompt, gave it CoT reasoning. (18.txt), and tried with the next wrongly labeled one (15), (full prompt, 19.txt)
• Tested this on everything except first 20, did pretty well
• Tried removing email, performance dropped of a cliff
• At this point, I am thinking that giving examples with reasoning helps (obviously)
• Tried to add 10 shots in for free, before the last one with reasoning, bad results

#### A.7.3.1 AutoCoT

• Develop dataset using this prompt (22.txt). Then ask it "Why?". If it disagrees, I say "It is actually not entrapment, please explain why." (accidentally duplicated email 23.txt)
• Just for fun, tried 0 shot full context (had to adjust verbalizer)
• tried this with special verbalizer which catches "This post does not meet the criteria for Entrapment."
• Tested my generated data, beat 0.5 F1
• Doing 10 more exemplars w autocot. Sometimes responds immediately with reasoning like "This post does not meet the criteria for Entrapment as the individual does not explicitly express feelings of being trapped or hopeless.", so just use that if so. Sometimes get refusal "I'm really sorry to hear that you're feeling this way, but I'm unable to provide the help that you need. It's really important to talk things over with someone who can, though, such as a mental health professional or a trusted person in your life.", just ask "Explain why it is not entrapment." after if so.
• performance didnt really improve, realized about 11% are getting -1, meaning not extracted properly.

Retrying with full words "Question" instead of Q, also for reasoning and answer.

• this led to higher inability to parse, at about 16%.

#### A.7.3.2 Developing Answer Extraction

• put first failing to parse one in (22), and developed a prompt for it.
• did worse: (0.42857142857142855, 0.5051546391752577, 0.8571428571428571, 0.2857142857142857)
• only using extracted label if have -1 helps slightly to (0.48, 0.61, 0.8571428571428571, 0.3333333333333333)
• going back to best performing prompt–10 QRA shot, and performing extraction with any -1s, doesnt help other than gently boosting accuracy, perhaps when it doesnt answer

#### A.7.3.3 Iterating on Email

• tried best perf, with no email
• tried with deduped email, worse results
• noticed that ones its unsure about often contained 1 labels that should be 0, so trying to "recover" these doesnt help
• try moving around exemplar order, performing extraction, didnt help
• triplicated email, didnt help

## A.8 Formally Defining a Prompt

"Prompt" is a widely used term, but uses and definitions differ widely across research. As a result, it is difficult to create a formal, mathematical definition for a prompt. In this section, we outline some formalisms for prompt engineering.

**As a conditioning Mechanism.**

Qiao et al. (2022) present the following definition, which involves the prompt T and a question Q as conditioning mechanisms on predicting the next token. Note that they appear to use Brown et al. (2020)'s original definition of prompt, which refers to the non-question part of the prompt (e.g. few-shot exemplars, instructions).

|A|
Y
p(A | T, Q) = p_LM(a_i | T, Q, a_1:i−1) (A.1)
i=1

Here, the prompt and question condition the pre-trained LLM p_LM. The a_1:i−1 are previously generated answer tokens and A a complete answer.

**Templating.**

The above formalization does not include the notion of maximizing a scoring or utility function (e.g. accuracy on a dataset), which prompts are often designed to do. Additionally, prompt engineers often seek to design prompt template rather than prompts. Here, we reformulate eq. (A.1) to include the prompt template:

|A|
Y
p(A | T(x∗)) = p_LM(a_i | T(x∗), a_1:i−1) (A.2)
i=1

We replace Q with x∗ ∈ D_eval, an item from a dataset (e.g., evaluation data). Additionally, we replace Q on the right side with T(x). T(·) is a prompt template: a function that accepts some item as input then returns a prompt that is used to condition the model.

**Few-Shot Prompting.**

Often, an important part of the prompting process is the use of few-shot exemplars.

D_train is training data (used to build the prompt) and X is a test set for evaluation.

D_train = {(x_1, y_1), (x_2, y_2), ..., (x_n, y_n)} (A.3)
X = {x∗_1, x∗_2, ..., x∗_m} (A.4)

In the few-shot setting, the prompt template function T(·) also takes as input one or more training samples X = {(x_i, y_i)}_n ⊂ D_train

|A|
Y
p(A | T(X, x∗)) = p_LM(a_i | T(X, x∗), a_1:i−1) (A.5)
i=1

**Optimization.**

As mentioned, it is often desirable to speak about improving prompts (prompt templates, that is) with respect to a scoring function, usually defined with respect to a dataset.

T∗ = argmax E_xi,yi∼D [S(p_LM(A|T(x_i)), y_i)] (A.6)
T

In this definition, we are evaluating over a dataset D with respect to the scoring function S(·). S(·) evaluates the output A, generated by the LLM conditioned on the prompt T(§⟩). y_i are labeled outputs that can be used by S.

In some cases, there may not be any labeled data y_i, and S(·) may be reference-free.

**Other considerations.**

These formalisms could be adapted to cater to CoT, retrieval systems, and more. Here we describe a simple setup which is most descriptive of the prompting process without adding too much complexity.

We also draw attention to the lesser known concept of answer engineering. E(A) is a transformation function over the raw LLM output that allows it to be compared to the ground truth.

A ∼ p_LM(A | T(x_i), y_i) (A.7)
T∗ = argmax E_xi,yi∼D [S(E(A), y_i)] (A.8)
T,E

## A.9 In-Context Learning Definitions Disambiguation

Brown et al. (2020) seemingly offer two different definitions for ICL. All bolding in this section is our own.

Recent work [RWC+19] attempts to do this via what we call "in-context learning", using the text input of a pretrained language model as a form of task specification: the model is conditioned on a natural language instruction and/or a few demonstrations of the task and is then expected to complete further instances of the task simply by predicting what comes next.

However, they later appear to define it as few-shot only:

For each task, we evaluate GPT-3 under 3 conditions: (a) "few-shot learning", or in-context learning where we allow as many demonstrations as will fit into the model's context window (typically 10 to 100), (b) "one-shot learning", where we allow only one demonstration, and (c) "zero-shot" learning, where no demonstrations are allowed and only an instruction in natural language is given to the model.

However, they include this image that clarifies the matter: Figure A.1: ICL from Brown et al. (2020).

Additionally, they explicitly state that ICL does not necessarily involve learning new tasks.

To avoid this confusion, we use the term "meta-learning" to capture the inner-loop / outer-loop structure of the general method, and the term "in context-learning" to refer to the inner loop of meta-learning. We further specialize the description to "zero-shot", "one-shot", or "few-shot" depending on how many demonstrations are provided at inference time. These terms are intended to remain agnostic on the question of whether the model learns new tasks from scratch at inference time or simply recognizes patterns seen during training – this is an important issue which we discuss later in the paper, but "meta-learning" is intended to encompass both possibilities, and simply describes the inner-outer loop structure.

We use Brown et al. (2020)'s broad definition, though note that practitioners often use ICL to refer to situations in which the model appears to be learning new tasks from the prompt. Our definition differs from Dong et al. (2023)'s formal definition, even though it is also derived from (Brown et al., 2020).

## A.10 Contributions

The following are the contributions made by the team members in various sections of this paper. Most authors conducted reviews of other sections as well.

**Advisors**

• Denis Peskoff: Assisted with paper organization and final review.
• Alexander Hoyle: Provided guidance on writing, meta-analysis approach, and ran automated baselines for case study.
• Shyamal Anadkat: Assisted with the overall review of the paper and the etymology and definitions.
• Jules White: Built trees for technique taxonomies.
• Marine Carpaut: Framed, reviewed and suggested papers for the multilingual section.
• Phillip Resnik: Principal Investigator

**SCS Labeling**

• Megan L. Rogers, Inna Goncearenco, Giuseppe Sarli, Igor Galynker: reviewed and gave advice for this section.

**Benchmarking and Agents**

• Konstantine Kahadze: Team leader for the Benchmarking section; managed MMLU benchmarking codebase, contributed to Security and Meta Analysis.
• Ashay Srivastava: Team leader for the Agents section, reviewed papers for human review, worked on the tool use agents section. Worked on the compilation of contributions.
• Hevander Da Costa: Contributed to the Benchmarking section and Meta Review datasets list, reviewed literature on LLM code generation and prompting techniques. Added literature review content to the Agents section.
• Feileen Li: Worked on the tool use agents section, assisted with the human paper review.

**Alignment and Security**

• Nishant Balepur: Team leader for the alignment section, helped with high-level discussions in benchmarking, and reviewed drafts.
• Sevien Schulhoff: Team leader for the security section and contributed to the benchmarking section.

**Related Works and Section Contributions**

• Chenglei Si: Suggested related works and edited section 2.2 and section 7.
• Pranav Sandeep Dulepet: Contributed definitions for section 2 and worked on segmentation and object detection in the multimodal section.
• HyoJung Han: Contributed to the Multimodal section, especially the speech+text part, and wrote the audio prompting section.
• Hudson Tao: Authored sections on image, video, and 3D within multimodal, reviewed papers for human review; maintained GitHub codebase, and built the project website.
• Amanda Liu: Authored taxonomic ontology sections, conducted background research for introduction and related work, developed code pipelines for meta-analysis graphs
• Sweta Agrawal: Team lead for evaluation section.
• Saurav Vidyadhara: Assisted with general review and revising taxonomy trees.
• Chau Pham: Assisted with meta review, including automated analysis of topics.

**Multilingual Prompting and Meta Analysis**

• Dayeon Ki: Led the Multilingual prompting section, conducted review on related papers, and wrote Section 3.1.
• Yinheng Li: Worked on section 2.2 text-based techniques, reviewed techniques, and contributed to drafting figure 2.2.
• Saloni Gupta: Wrote tests for paper compilation, helped set up paper pipeline, and worked on the code diagram and grammar for the paper.
• Gerson Kroiz: Involved with section 1.1 and defining a prompt.
• Aayush Gupta: Contributed to the Meta Analysis, compiling papers, and generating visualization graphs.
• Michael Ilie: Co-Lead Author, managed codebase, ran experiments, collected data, and helped with various sections including the PRISMA review figure and the SCS prompting case study.
• Sander Schulhoff: Lead Author
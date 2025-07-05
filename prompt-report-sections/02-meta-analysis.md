# 2 A Meta-Analysis of Prompting

## 2.1 Systematic Review Process

3,677 from arXiv 2,087 from SS, 639 from ACL = 4797 Records

-550

In order to robustly collect a dataset of sources

for this paper, we ran a systematic literature re-

4,247 Records after Title 

1,661 papers human reviewed

Deduplication

view grounded in the PRISMA process (Page et al., 

2021) (Figure 2.1). We host this dataset on Hug-

-316

316 papers excluded

gingFace 4 and present a datasheet (Gebru et al., 

2021) for the dataset in Appendix A.3. Our main 3,931 Records after Human 

Check if paper contains the 

Review

word "prompt" 

data sources were arXiv, Semantic Scholar, and

ACL. We query these databases with a list of

-1,579

1,579 papers excluded

44 keywords narrowly related to prompting and

prompt engineering (Appendix A.4). 

2,352 Records after 

removing papers that don't 

1,071 papers AI reviewed

contain the word "prompt" 

### 2.1.1 The Pipeline

-787

787 papers excluded

In this section, we introduce our data scraping

pipeline, which includes both human and LLM-

After The PRISMA Review Process, 

1,565 records included in quantitative analysis. 

assisted review.5 As an initial sample to establish filtering critera, we retrieve papers from arXiv

Figure 2.1: The PRISMA systematic literature review

based on a simple set of keywords and boolean

process. We accumulate 4,247 unique records from

rules (A.4). Then, human annotators label a sample which we extract 1,565 relevant records. 

of 1,661 articles from the arXiv set for the follow-

ing criteria:

## 2.2 Text-Based Techniques

1. Include if the paper proposes a novel prompt-

We now present a comprehensive taxonomical on-

ing technique. 

tology of 58 text-based prompting techniques, bro-

ken into 6 major categories (Figure 2.2). Although 2. Include if the paper strictly covers hard prefix

some of the techniques might fit into multiple cate-

prompts. 

gories, we place them in a single category of most

relevance. 

3. Exclude if the paper focuses on training by

backpropagating gradients. 

### 2.2.1 In-Context Learning (ICL)

4. Include if the paper uses a masked frame

ICL refers to the ability of GenAIs to learn skills

and/or window for non-text modalities. 

and tasks by providing them with exemplars and or

relevant instructions within the prompt, without the

need for weight updates/retraining (Brown et al., 

A set of 300 articles are reviewed independently

2020; Radford et al., 2019b). These skills can be by two annotators, with 92% agreement (Krippen-learned from exemplars (Figure 2.4) and/or instruc-dorff's *α *= Cohen's *κ *= 81%). Next, we develop tions (Figure 2.5). Note that the word "learn" is a prompt using gpt-4-1106-preview to classify the

misleading. ICL can simply be task specification–

remaining articles (Appendix A.5). We validate the skills are not necessarily new, and can have

the prompt against 100 ground-truth annotations, 

already been included in the training data (Figure

achieving 89% precision and 75% recall (for an *F * 1

2.6). See Appendix A.9 for a discussion of the use of 81%). The combined human and LLM annota-of this term. Significant work is currently being

tions generate a final set of 1,565 papers. 

done on optimizing (Bansal et al., 2023) and un-4https://huggingface.co/datasets/PromptSystematicReview/Prompt\_Systematic\_Re

derstanding (Si vie

et w\_Dataset

al., 2023a; Štefánik and Kadlčík, 

5Using gpt-4-1106-preview

2023) ICL. 

8

Emotion Prompting 2.2.1.3

Role Prompting 2.2.1.3

Style Prompting 2.2.1.3

S2A 2.2.1.3

Zero-Shot 2.2.1.3

SimToM 2.2.1.3

RaR 2.2.1.3

RE2 2.2.1.3

Self-Ask 2.2.1.3

Exemplar Generation

SG-ICL 2.2.1.2

Exemplar Ordering 2.2.1.1

Analogical Prompting

Few-Shot 2.2.1

Exemplar Selection

KNN 2.2.1.2

2.2.2.1

2.2.1.2

Vote-K 2.2.1.2

Step-Back Prompting

Instruction Selection 2.2.1.1

2.2.2.1

Zero-Shot CoT 2.2.2.1

Thread-of-Thought

(ThoT) 2.2.2.1

Tab-CoT 2.2.2.1

Chain-of-Thought

Active-Prompt 2.2.2.2

Thought Generation 2.2.2

(CoT) 2.2.2

Auto-CoT 2.2.2.2

COSP 2.2.4

Complexity-Based 2.2.2.2

DENSE 2.2.4

Contrastive 2.2.2.2

DiVeRSe 2.2.4

Few-Shot CoT 2.2.2.2

Memory-of-Thought

2.2.2.2

Max Mutual

Information 2.2.4

Text-Base Prompt. Tech. 

Uncertainty-Routed

CoT 2.2.2.2

Meta-CoT 2.2.4

Ensembling 2.2.4

Prompt Mining 2.2.1.2

MoRE 2.2.4

AutoDiCoT 6.2.3.3

Self-Consistency 2.2.4

Universal

Self-Consistency 2.2.4

USP 2.2.4

Prompt Paraphrasing 2.2.4

Chain-of-Verification 2.2.5

Self-Calibration 2.2.5

Self-Refine 2.2.5

Self-Criticism 2.2.5

Self-Verification 2.2.5

ReverseCoT 2.2.5

Cumulative Reason. 2.2.5

DECOMP 2.2.3

Faithful CoT 2.2.3

Least-to-Most 2.2.3

Plan-and-Solve 2.2.3

Decomposition 2.2.3

Program-of-Thought 2.2.3

Recurs.-of-Thought 2.2.3

Skeleton-of-Thought 2.2.3

Tree-of-Thought 2.2.3

Metacognitive 2.2.3

Figure 2.2: All text-based prompting techniques from our dataset. 

9

1. Exemplar Quantity

2. Exemplar Ordering

Include as many exemplars as 

Randomly order exemplars\*

2\+2: four

possible\*

4\+5: nine

Trees are beautiful: Happy

I am so mad: Angry

I hate Pizza: Angry

I love life: Happy

8\+0:

Squirrels are so cute: Happy

I hate my boss: Angry

YouTube Ads Suck: Angry

Life is good: Happy

I'm so excited: 

I'm so excited: 

Figure 2.4: ICL exemplar prompt

I love life: Happy

Life is good: Happy

Trees are beautiful: Happy

I am so mad: Angry

I'm so excited: 

I hate my boss: Angry

I'm so excited: 

Extract all words that have 3 of the same

3. Exemplar Label Distribution

4. Exemplar Label Quality

letter and at least 3 other letters from the

Provide a balanced label 

Ensure exemplars are labeled 

following text: {TEXT}

distribution\*

correctly\*

I am so mad: Angry

I am so mad: Angry

I love life: Happy

I love life: Happy

I hate my boss: Angry

I hate my boss: Angry

Figure 2.5: ICL instruction prompt

Life is good: Happy

Life is good: Happy

I'm so excited: 

I'm so excited: 

I am so mad: Angry

I am so mad: Happy

People are so dense: Angry

I love life: Angry

Exemplar Quantity

Increasing the quantity of ex-

I hate my boss: Angry

I hate my boss: Angry

Life is good: Happy

Life is good: Happy

emplars in the prompt generally improves model

I'm so excited: 

I'm so excited: 

performance, particularly in larger models (Brown

5. Exemplar Format

6. Exemplars Similarity

et al., 2020). However, in some cases, the bene-Choose a common format\*

Select similar exemplars to 

the test instance\*

fits may diminish beyond 20 exemplars (Liu et al., 

2021). In the case of long context LLMs, addi-Im hyped\!: Happy

Im hyped\!: Happy

Im not very excited: Angry

Im not very excited: Angry

tional exemplars continue to increase performance, 

I'm so excited: 

I'm so excited: 

though efficiency varies depending on task and

model (Agarwal et al., 2024; Bertsch et al., 2024; 

Trees are nice===Happy

Trees are beautiful: Happy

Jiang et al., 2024). 

YouTube Ads Suck===Angry

YouTube Ads Suck: Angry

I'm so excited===

I'm so excited: 

Exemplar Ordering

The order of exemplars af-

fects model behavior (Lu et al., 2021; Kumar and

Figure 2.3: We highlight six main design decisions

Talukdar, 2021; Liu et al., 2021; Rubin et al., 2022). 

when crafting few-shot prompts. ∗Please note that rec-

On some tasks, exemplar order can cause accuracy

ommendations here do not generalize to all tasks; in

some cases, each of them could hurt performance. 

to vary from sub-50% to 90%\+ (Lu et al., 2021). 

Exemplar Label Distribution

As in traditional

Few-Shot Prompting

(Brown et al., 2020) is the

supervised machine learning, the distribution of

paradigm seen in Figure 2.4, where the GenAI exemplar labels in the prompt affects behavior. For

learns to complete a task with only a few examples

example, if 10 exemplars from one class and 2

(exemplars). Few-shot prompting is a special case

exemplars of another class are included, this may

of Few-Shot Learning (FSL) (Fei-Fei et al., 2006; 

cause the model to be biased toward the first class. 

Wang et al., 2019), but does not require updating Exemplar Label Quality

Despite the general ben-

of model parameters

efit of multiple exemplars, the necessity of strictly

valid demonstrations is unclear. Some work (Min

#### 2.2.1.1 Few-Shot Prompting Design Decisions

et al., 2022) suggests that the accuracy of labels is Selecting exemplars for a prompt is a difficult task–

irrelevant—providing models with exemplars with

performance depends significantly on various fac-

incorrect labels may not negatively diminish per-

tors of the exemplars (Dong et al., 2023), and only formance. However, under certain settings, there

a limited number of exemplars fit in the typical

is a significant impact on performance (Yoo et al., 

LLM's context window. We highlight six separate

2022). Larger models are often better at handling design decisions, including the selection and or-incorrect or unrelated labels (Wei et al., 2023c). 

der of exemplars that critically influence the output

It is important to discuss this factor, since if you

quality (Zhao et al., 2021a; Lu et al., 2021; Ye and

are automatically constructing prompts from large

Durrett, 2023) (Figure 2.3). 

datasets that may contain inaccuracies, it may be

10

generated with respect to *Dtest*

Translate the word "cheese" to French. 

*xi*

at test time. Here

is the prompt template we will use for this section, 

following the 'input: output' format (Figure 2.4):

Figure 2.6: ICL from training data prompt. In this

version of ICL, the model is not learning a new skill, 

{Exemplars}

but rather using knowledge likely in its training set. 

*Dtest*

*xi*

:

necessary to study how label quality affects your

results. 

Figure 2.7: Few-Shot Prompting Template

Exemplar Format

The formatting of exemplars

also affects performance. One of the most common

K-Nearest Neighbor (KNN)

(Liu et al., 2021) is

formats is "Q: {input}, A: {label}", but the optimal

part of a family of algorithms that selects exemplars

format may vary across tasks; it may be worth

similar to *Dtest*

*xi*

to boost performance. Although ef-

trying multiple formats to see which performs best. 

fective, employing KNN during prompt generation

There is some evidence to suggest that formats that

may be time and resource intensive. 

occur commonly in the training data will lead to

better performance (Jiang et al., 2020). 

Vote-K

(Su et al., 2022) is another method to

select similar exemplars to the test sample. In one

Exemplar Similarity

Selecting exemplars that

stage, a model proposes useful unlabeled candidate

are similar to the test sample is generally bene-

exemplars for an annotator to label. In the sec-

ficial for performance (Liu et al., 2021; Min et al., 

ond stage, the labeled pool is used for Few-Shot

2022). However, in some cases, selecting more Prompting. Vote-K also ensures that newly added

diverse exemplars can improve performance (Su

exemplars are sufficiently different than existing

et al., 2022; Min et al., 2022). 

ones to increase diversity and representativeness. 

Instruction Selection

While instructions are re-

Self-Generated In-Context Learning (SG-ICL)

quired to guide LLMs in zero-shot prompts (Wei

(Kim et al., 2022) leverages a GenAI to automati-

et al., 2022a), the benefits of adding instructions cally generate exemplars. While better than zero-before exemplars in few-shot prompts is less clear. 

shot scenarios when training data is unavailable, 

Ajith et al. (2024) show that generic, task-agnostic the generated samples are not as effective as actual

instructions (i.e., no instruction or "Complete the

data. 

following task:") improve classification and ques-

tion answering accuracy over task-specific ones

Prompt Mining

(Jiang et al., 2020) is the process

(e.g., What is the answer to this question?) conclud-

of discovering optimal "middle words" in prompts

ing instruction-following abilities can be achieved

through large corpus analysis. These middle words

via exemplars alone. While they may not improve

are effectively prompt templates. For example, in-

correctness, instructions in few-shot prompts can

stead of using the common "Q: A:" format for few-

still guide auxiliary output attributes like writing

shot prompts, there may exist something similar

style (Roy et al., 2023). 

that occurs more frequently in the corpus. Formats

which occur more often in the corpus will likely

#### 2.2.1.2 Few-Shot Prompting Techniques

lead to improved prompt performance. 

Considering all of these factors, Few-Shot Prompt-

ing can be very difficult to implement effectively. 

More Complicated Techniques

such as LENS

We now examine techniques for Few-Shot Prompt-

(Li and Qiu, 2023a), UDR (Li et al., 2023f), and ing in the supervised setting. 

Ensembling ap-

Active Example Selection (Zhang et al., 2022a)

proaches can also benefit Few-Shot Prompting, but

leverage iterative filtering, embedding and retrieval, 

we discuss them separately (Section 2.2.4). 

and reinforcement learning, respectively. 

Assume we have a training dataset, *Dtrain*, 

which contains multiple inputs *Dtrain*

#### 2.2.1.3 Zero-Shot Prompting Techniques

*xi*

and outputs

*Dtrain*

In contrast to Few-Shot Prompting, Zero-Shot

*yi*

, which can be used to few-shot prompt a

GenAI (rather than performing gradient-based up-

Prompting uses zero exemplars. There are a num-

dates). Assume that this prompt can be dynamically

ber of well-known standalone zero-shot techniques

11

as well as zero-shot techniques combined with an-Q: Jack has two baskets, each containing

other concept (e.g. Chain of Thought), which we

three balls. How many balls does Jack have

discuss later (Section 2.2.2). 

in total? 

Role Prompting

(Wang et al., 2023j; Zheng

A: One basket contains 3 balls, so two bas-

et al., 2023d) , also known as persona prompting kets contain 3 \* 2 = 6 balls. 

(Schmidt et al., 2023; Wang et al., 2023l), assigns a Q: {QUESTION}

specific role to the GenAI in the prompt. For exam-

A:

ple, the user might prompt it to act like "Madonna" 

or a "travel writer". This can create more desir-

Figure 2.8: A One-Shot Chain-of-Thought Prompt. 

able outputs for open-ended tasks (Reynolds and

McDonell, 2021) and in some cases may improve accuracy on benchmarks (Zheng et al., 2023d). 

in reasoning benchmarks, especially with complex

questions. 

Style Prompting

(Lu et al., 2023a) involves spec-

ifying the desired style, tone, or genre in the prompt

Self-Ask

(Press et al., 2022) prompts LLMs to

to shape the output of a GenAI. A similar effect

first decide if they need to ask follow up questions

can be achieved using role prompting. 

for a given prompt. If so, the LLM generates these

questions, then answers them and finally answers

Emotion Prompting

(Li et al., 2023a) incorpo-

the original question. 

rates phrases of psychological relevance to humans

(e.g., "This is important to my career") into the ### 2.2.2 Thought Generation

prompt, which may lead to improved LLM perfor-

Thought generation encompasses a range of tech-

mance on benchmarks and open-ended text genera-

niques that prompt the LLM to articulate its reason-

tion. 

ing while solving a problem (Zhang et al., 2023c). 

System

2

Attention

(S2A)

(Weston

and

Chain-of-Thought (CoT) Prompting

(Wei et al., 

Sukhbaatar, 2023) first asks an LLM to rewrite

2022b) leverages few-shot prompting to encour-the prompt and remove any information unrelated

age the LLM to express its thought process before

to the question therein. Then, it passes this new

delivering its final answer.6 This technique is occa-prompt into an LLM to retrieve a final response. 

sionally referred to as Chain-of-Thoughts (Tutunov

SimToM

(Wilf et al., 2023) deals with compli-

et al., 2023; Besta et al., 2024; Chen et al., 2023d). 

cated questions which involve multiple people or

It has been demonstrated to significantly enhance

objects. Given the question, it attempts to establish

the LLM's performance in mathematics and reason-

the set of facts one person knows, then answer the

ing tasks. In Wei et al. (2022b), the prompt includes question based only on those facts. This is a two

an exemplar featuring a question, a reasoning path, 

prompt process and can help eliminate the effect of

and the correct answer (Figure 2.8). 

irrelevant information in the prompt. 

#### 2.2.2.1 Zero-Shot-CoT

Rephrase and Respond (RaR)

(Deng et al., 2023)

The most straightforward version of CoT contains

instructs the LLM to rephrase and expand the ques-

zero exemplars. It involves appending a thought

tion before generating the final answer. For ex-

inducing phrase like "Let's think step by step." 

ample, it might add the following phrase to the

(Kojima et al., 2022) to the prompt. Other sug-question: "Rephrase and expand the question, and

gested thought-generating phrases include "First, 

respond". This could all be done in a single pass

let's think about this logically" (Kojima et al., 

or the new question could be passed to the LLM

2022). Zhou et al. (2022b) uses LLMs to generate separately. RaR has demonstrated improvements

"Let's work this out in a step by step way to be

on multiple benchmarks. 

sure we have the right answer". Yang et al. (2023a)

searches for an optimal thought inducer. Zero-Shot-

Re-reading (RE2)

(Xu et al., 2023) adds the

6

phrase "Read the question again:" to the prompt in We note that such techniques are often described using

words like "think" that anthropomorphize models. We attempt addition to repeating the question. Although this is

not to use this language, but do use original authors' language such a simple technique, it has shown improvement

where appropriate. 

12

CoT approaches are attractive as they don't require benchmark for both GPT-4 and Gemini Ultra mod-exemplars and are generally task agnostic. 

els. 

Step-Back Prompting

(Zheng et al., 2023c) is a

Complexity-based Prompting

(Fu et al., 2023b)

modification of CoT where the LLM is first asked

involves two major modifications to CoT. First, it

a generic, high-level question about relevant con-

selects complex examples for annotation and in-

cepts or facts before delving into reasoning. This

clusion in the prompt, based on factors like ques-

approach has improved performance significantly

tion length or reasoning steps required. Second, 

on multiple reasoning benchmarks for both PaLM-

during inference, it samples multiple reasoning

2L and GPT-4. 

chains (answers) and uses a majority vote among

Analogical Prompting

(Yasunaga et al., 2023)

chains exceeding a certain length threshold, under

is similar to SG-ICL, and automatically generates

the premise that longer reasoning indicates higher

exemplars that include CoTs. It has demonstrated

answer quality. This technique has shown improve-

improvements in mathematical reasoning and code

ments on three mathematical reasoning datasets. 

generation tasks. 

Active Prompting

(Diao et al., 2023) starts with

Thread-of-Thought (ThoT) Prompting

(Zhou

some training questions/exemplars, asks the LLM

et al., 2023) consists of an improved thought in-to solve them, then calculates uncertainty (disagree-

ducer for CoT reasoning. Instead of "Let's think

ment in this case) and asks human annotators to

step by step," it uses "Walk me through this context rewrite the exemplars with highest uncertainty. 

in manageable parts step by step, summarizing and

Memory-of-Thought Prompting

(Li and Qiu, 

analyzing as we go." This thought inducer works

2023b) leverage unlabeled training exemplars to well in question-answering and retrieval settings, 

build Few-Shot CoT prompts at test time. Before

especially when dealing with large, complex con-

test time, it performs inference on the unlabeled

texts. 

training exemplars with CoT. At test time, it re-

Tabular Chain-of-Thought (Tab-CoT)

(Jin and

trieves similar instances to the test sample. This

Lu, 2023) consists of a Zero-Shot CoT prompt that technique has shown substantial improvements in

makes the LLM output reasoning as a markdown

benchmarks like Arithmetic, commonsense, and

table. This tabular design enables the LLM to im-

factual reasoning. 

prove the structure and thus the reasoning of its

output. 

Automatic Chain-of-Thought (Auto-CoT) Prompt-

ing

(Zhang et al., 2022b) uses Wei et al. (2022b)'s #### 2.2.2.2 Few-Shot CoT

Zero-Shot prompt to automatically generate chains

This set of techniques presents the LLM with mul-

of thought. These are then used to build a Few-Shot

tiple exemplars, which include chains-of-thought. 

CoT prompt for a test sample. 

This can significantly enhance performance. This

technique is occasionally referred to as Manual-

### 2.2.3 Decomposition

CoT (Zhang et al., 2022b) or Golden CoT (Del and

Significant research has focused on decomposing

Fishel, 2023). 

complex problems into simpler sub-questions. This

Contrastive CoT Prompting

(Chia et al., 2023)

is an effective problem-solving strategy for humans

adds both exemplars with incorrect and correct ex-

as well as GenAI (Patel et al., 2022). Some decom-planations to the CoT prompt in order to show the

position techniques are similar to thought-inducing

LLM how not to reason. This method has shown

techniques, such as CoT, which often naturally

significant improvement in areas like Arithmetic

breaks down problems into simpler components. 

Reasoning and Factual QA. 

However, explicitly breaking down problems can

further improve LLMs' problem solving ability. 

Uncertainty-Routed CoT Prompting

(Google, 

2023) samples multiple CoT reasoning paths, then Least-to-Most Prompting

(Zhou et al., 2022a)

selects the majority if it is above a certain thresh-

starts by prompting a LLM to break a given prob-

old (calculated based on validation data). If not, it

lem into sub-problems without solving them. Then, 

samples greedily and selects that response. This

it solves them sequentially, appending model re-

method demonstrates improvement on the MMLU

sponses to the prompt each time, until it arrives

13

at a final result. This method has shown signif-mathematical and programming-related tasks but

icant improvements in tasks involving symbolic

is less effective for semantic reasoning tasks. 

manipulation, compositional generalization, and

Faithful Chain-of-Thought

(Lyu et al., 2023)

mathematical reasoning. 

generates a CoT that has both natural language and

Decomposed Prompting (DECOMP)

(Khot

symbolic language (e.g. Python) reasoning, just

et al., 2022) Few-Shot prompts a LLM to show it like Program-of-Thoughts. However, it also makes

how to use certain functions. These might include

use of different types of symbolic languages in a

things like string splitting or internet searching; 

task-dependent fashion. 

these are often implemented as separate LLM calls. 

Skeleton-of-Thought

(Ning et al., 2023) focuses

Given this, the LLM breaks down its original prob-

on accelerating answer speed through paralleliza-

lem into sub-problems which it sends to different

tion. Given a problem, it prompts an LLM to create

functions. It has shown improved performance over

a skeleton of the answer, in a sense, sub-problems

Least-to-Most prompting on some tasks. 

to be solved. Then, in parallel, it sends these ques-

Plan-and-Solve Prompting

(Wang et al., 2023f)

tions to a LLM and concatenates all the outputs to

consists of an improved Zero-Shot CoT prompt, 

get a final response. 

"Let's first understand the problem and devise a

Metacognitive Prompting

(Wang and Zhao, 

plan to solve it. Then, let's carry out the plan and

2024) attempts to make the LLM mirror human solve the problem step by step". This method gener-metacognitive processes with a five part prompt

ates more robust reasoning processes than standard

chain, with steps including clarifying the question, 

Zero-Shot-CoT on multiple reasoning datasets. 

preliminary judgement, evaluation of response, de-

cision confirmation, and confidence assessment. 

Tree-of-Thought (ToT)

(Yao et al., 2023b), also

known as Tree of Thoughts, (Long, 2023), creates a ### 2.2.4 Ensembling

tree-like search problem by starting with an initial

problem then generating multiple possible steps in

In GenAI, ensembling is the process of using multi-

the form of thoughts (as from a CoT). It evaluates

ple prompts to solve the same problem, then aggre-

the progress each step makes towards solving the

gating these responses into a final output. In many

problem (through prompting) and decides which

cases, a majority vote—selecting the most frequent

steps to continue with, then keeps creating more

response—is used to generate the final output. En-

thoughts. ToT is particularly effective for tasks that

sembling techniques reduce the variance of LLM

require search and planning. 

outputs and often improving accuracy, but come

with the cost of increasing the number of model

Recursion-of-Thought

(Lee and Kim, 2023) is

calls needed to reach a final answer. 

similar to regular CoT. However, every time it en-

Demonstration Ensembling (DENSE)

(Khalifa

counters a complicated problem in the middle of its

et al., 2023) creates multiple few-shot prompts, reasoning chain, it sends this problem into another

each containing a distinct subset of exemplars from

prompt/LLM call. After this is completed, the an-

the training set. Next, it aggregates over their out-

swer is inserted into the original prompt. In this

puts to generate a final response. 

way, it can recursively solve complex problems, in-

cluding ones which might otherwise run over that

Mixture of Reasoning Experts (MoRE)

(Si et al., 

maximum context length. This method has shown

2023d) creates a set of diverse reasoning experts improvements on arithmetic and algorithmic tasks. 

by using different specialized prompts for different

Though implemented using fine-tuning to output a

reasoning types (such as retrieval augmentation

special token that sends sub-problem into another

prompts for factual reasoning, Chain-of-Thought

prompt, it could also be done only through prompt-

reasoning for multi-hop and math reasoning, and

ing. 

generated knowledge prompting for commonsense

reasoning). The best answer from all experts is

Program-of-Thoughts

(Chen et al., 2023d) uses

selected based on an agreement score. 

LLMs like Codex to generate programming code

as reasoning steps. A code interpreter executes

Max Mutual Information Method

(Sorensen

these steps to obtain the final answer. It excels in

et al., 2022) creates multiple prompt templates with 14

varied styles and exemplars, then selects the opti-Prompt Paraphrasing

(Jiang et al., 2020) trans-

mal template as the one that maximizes mutual

forms an original prompt by changing some of the

information between the prompt and the LLM's

wording, while still maintaining the overall mean-

outputs. 

ing. It is effectively a data augmentation technique

that can be used to generate prompts for an ensem-

Self-Consistency

(Wang et al., 2022) is based

ble. 

on the intuition that multiple different reasoning

paths can lead to the same answer. This method

### 2.2.5 Self-Criticism

first prompts the LLM multiple times to perform

CoT, crucially with a non-zero temperature to elicit

When creating GenAI systems, it can be useful to

diverse reasoning paths. Next, it uses a majority

have LLMs criticize their own outputs (Huang et al., 

vote over all generated responses to select a final

2022). This could simply be a judgement (e.g., is response. Self-Consistency has shown improve-this output correct) or the LLM could be prompted

ments on arithmetic, commonsense, and symbolic

to provide feedback, which is then used to improve

reasoning tasks. 

the answer. Many approaches to generating and

integrating self-criticism have been developed. 

Universal Self-Consistency

(Chen et al., 2023e)

is similar to Self-Consistency except that rather

Self-Calibration

(Kadavath et al., 2022) first

than selecting the majority response by program-

prompts an LLM to answer a question. Then, it

matically counting how often it occurs, it inserts

builds a new prompt that includes the question, the

all outputs into a prompt template that selects the

LLM's answer, and an additional instruction asking

majority answer. This is helpful for free-form text

whether the answer is correct. This can be useful

generation and cases where the same answer may

for gauging confidence levels when applying LLMs

be output slightly differently by different prompts. 

when deciding when to accept or revise the original

answer. 

Meta-Reasoning over Multiple CoTs

(Yoran

et al., 2023) is similar to universal Self-Self-Refine

(Madaan et al., 2023) is an iterative

Consistency; it first generates multiple reasoning

framework where, given an initial answer from the

chains (but not necessarily final answers) for a

LLM, it prompts the same LLM to provide feed-

given problem. Next, it inserts all of these chains

back on the answer, and then prompts the LLM to

in a single prompt template then generates a final

improve the answer based on the feedback. This

answer from them. 

iterative process continues until a stopping condi-

tion is met (e.g., max number of steps reached). 

DiVeRSe

(Li et al., 2023i)

creates multiple

Self-Refine has demonstrated improvement across

prompts for a given problem then performs Self-

a range of reasoning, coding, and generation tasks. 

Consistency for each, generating multiple reason-

ing paths. They score reasoning paths based on

Reversing

Chain-of-Thought

(RCoT)

(Xue

each step in them then select a final response. 

et al., 2023) first prompts LLMs to reconstruct Consistency-based

Self-adaptive

Prompting

the problem based on generated answer. Then, it

(COSP)

(Wan et al., 2023a) constructs Few-Shot

generates fine-grained comparisons between the

CoT prompts by running Zero-Shot CoT with

original problem and the reconstructed problem

Self-Consistency on a set of examples then

as a way to check for any inconsistencies. These

selecting a high agreement subset of the outputs

inconsistencies are then converted to feedback for

to be included in the final prompt as exemplars. It

the LLM to revise the generated answer. 

again performs Self-Consistency with this final

Self-Verification

prompt. 

(Weng et al., 2022)

gener-

ates multiple candidate solutions with Chain-of-

Universal Self-Adaptive Prompting (USP)

(Wan

Thought (CoT). It then scores each solution by

et al., 2023b) builds upon the success of COSP, aim-masking certain parts of the original question and

ing to make it generalizable to all tasks. USP makes

asking an LLM to predict them based on the rest

use of unlabeled data to generate exemplars and a

of the question and the generated solution. This

more complicated scoring function to select them. 

method has shown improvement on eight reasoning

Additionally, USP does not use Self-Consistency. 

datasets. 

15

Chain-of-Verification

(COVE)

(Dhuliawala

any mentioned dataset or model from the body of

et al., 2023) first uses an LLM to generate an papers in our dataset. After, we manually filtered

answer to a given question. Then, it creates a

out results that were not models or datasets. The

list of related questions that would help verify

citation counts were acquired by searching items

the correctness of the answer. Each question is

from the finalized list on Semantic Scholar. 

answered by the LLM, then all the information

is given to the LLM to produce the final revised

## 2.4 Prompt Engineering

answer. This method has shown improvements in

In addition to surveying prompting techniques, we

various question-answering and text-generation

also review prompt engineering techniques, which

tasks. 

are used to automatically optimize prompts. We

Cumulative Reasoning

(Zhang et al., 2023b)

discuss some techniques that use gradient updates, 

first generates several potential steps in answering

since the set of prompt engineering techniques is

the question. It then has a LLM evaluate them, de-

much smaller than that of prompting techniques. 

ciding to either accept or reject these steps. Finally, 

Meta Prompting

is the process of prompting a

it checks whether it has arrived at the final answer. 

LLM to generate or improve a prompt or prompt

If so, it terminates the process, but otherwise it

template (Reynolds and McDonell, 2021; Zhou

repeats it. This method has demonstrated improve-

et al., 2022b; Ye et al., 2023). This is often done ments in logical inference tasks and mathematical

without any scoring mechanism, using just a sim-

problem. 

ple template (Figure 2.12). However, other works present more complex uses of meta-prompting, 

## 2.3 Prompting Technique Usage

with multiple iterations and scoring mechanisms

As we have just seen, there exist many text-based

Yang et al. (2023a); Fernando et al. (2023). 

prompting techniques. However, only a small sub-

set of them are commonly used in research and in

Improve the following prompt: {PROMPT}

industry. We measure technique usage by proxy of

measuring the number of citations by other papers

in our dataset. We do so with the presumption that

Figure 2.12: A simple Meta Prompting template. 

papers about prompting are more likely to actually

use or evaluate the cited technique. We graph the

AutoPrompt

(Shin et al., 2020b) uses a frozen

top 25 papers cited in this way from our dataset and

LLM as well as a prompt template that includes

find that most of them propose new prompting tech-

some "trigger tokens", whose values are updated

niques (Figure 2.11). The prevalence of citations via backpropogation at training time. This is a

for Few-Shot and Chain-of-Thought prompting is

version of soft-prompting. 

unsurprising and helps to establish a baseline for

understanding the prevalence of other techniques. 

Automatic Prompt Engineer (APE)

(Zhou et al., 

2022b) uses a set of exemplars to generate a Zero-### 2.3.1 Benchmarks

Shot instruction prompt. It generates multiple pos-

In prompting research, when researchers propose

sible prompts, scores them, then creates variations

a new technique, they usually benchmark it across

of the best ones (e.g. by using prompt paraphras-

multiple models and datasets. This is important to

ing). It iterates on this process until some desider-

prove the utility of the technique and examine how

ata are reached. 

it transfers across models. 

Gradientfree

Instructional

Prompt

Search

In order to make it easier for researchers propos-

(GrIPS)

(Prasad et al., 2023) is similar to APE, ing new techniques to know how to benchmark

but uses a more complex set of operations includ-

them, we quantitatively examine which models

ing deletion, addition, swapping, and paraphrasing

(Figure 2.9) and what benchmark datasets (Fig-in order to create variations of a starting prompt. 

ure 2.10) are being used. Again, we measure usage by how many times papers in our dataset cite the

Prompt Optimization with Textual Gradients (Pro-

benchmark datasets and models. 

TeGi)

(Pryzant et al., 2023) is a unique approach To find which datasets and models are being

to prompt engineering that improves a prompt tem-

used, we prompted GPT-4-1106-preview to extract

plate through a multi-step process. First, it passes

16

100

200

300

Count 400 500

1

1 Counts 1

1

0

Few-Shot L

0

0

0

0

0

1

2

3

GPT

Zer

Good In-Conte

-3

o

BER

-Shot R ear

GPT

Counts of Model Mentions in Dataset

R

T

ning\*

easoning\*

-4

oBER

xt Examples

P Ta

Pr Self

aLM

ompt Or

LLaMA

-Consistency\*

Least-to

BAR

der Sensitivity

-Most P

T

Codex

InstructGPT

OPT

P

Human-L r

r

ompting\*

ompt R

BLOOM

evel P etrieval

FL

r

Citation Counts of P

AN

Model Name

ompting

Automatic CoT\*

CLIP

SAM

BioBER

T

Lambda

Comple

r

P

Self

ee of Thoughts\*

r

T

Flamingo

-Ask\*

ogram of Thoughts\*

Vision T

xity

BLOOMZ

-Based P

CoCoOp

ransfor

r

Decomposed P ompting\*

mer

Self

BLIP

-R

-2

Codellama

efine\*

VLP

r

Self ompting\*

In-conte

F

-Evaluation\*

Maieutic P

inBER

Gr

LLaV

GatorT

xt L

T

ounding DINO

r

ear ompting\*

Dr

A

P

ning Survey

Graph of Thoughts\*

eamF ron

rompting T

LLMs as Optimizers

usion

A

Plan-and-Solve P

ctive P

r

r

echniques

ompting T

ompting\*

rompting\*

Faithful CoT\*

Support Examples

Figure 2.9: Citation Counts of GenAI Models

kNN P

Unified Demo R

200

400

600

800

Number of Mentions

rompting\*

0

Tree- etriever\*

GSM8K

of

Step-

-Thought\*

echniques

Automate-CoT\*

Aware V

MML

Self erification\*

-Generated ICL\*

Question Decomposition

U

Dataset Mentions in P

Deductive V

BBH

CommonsenseQA

Cumulative R

erification\*

Chain-

Self

easoning\*

-A of-V

daptive P

Demonstration Ensembling

HellaSwag

erification\*

Dataset Name

rompting\*

Memory

BIG-bench

Rephrase and R

-of-Thought\*

WinoGrande

espond\*

QASC

apers

AQUA-RAT

T

Figure 2.11: Citation Counts of Prompting Techniques. 

ruthfulQA

The top 25 papers in our dataset, measured by how often

they are cited by other papers in our dataset. Most pa-

pers here are prompting techniques\*, and the remaining

papers contains prompting advice. 

Figure 2.10: Citation Counts of Datasets

17

LLM Response

a batch of inputs through the template, then passes

the output, ground truth, and prompt into another

Likely Negative

prompt that criticizes the original prompt. It gener-

Answer Shape:

A span of tokens

This is negative

ates new prompts from these criticisms then uses

NEGATIVE \! 

a bandit algorithm (Gabillon et al., 2011) to select one. ProTeGi demonstrates improvements over

methods like APE and GRIPS. 

Answer Space:

Answer Extraction:

All possible spans of tokens

Select the proper label

RLPrompt

(Deng et al., 2022) uses a frozen LLM

with an unfrozen module added. It uses this LLM to

Figure 2.13: An annotated output of a LLM output for a

generate prompt templates, scores the templates on

labeling task, which shows the three design decisions of

answer engineering: the choice of answer shape, space, 

a dataset, and updates the unfrozen module using

and extractor. Since this is an output from a classifi-

Soft Q-Learning (Guo et al., 2022). Interestingly, cation task, the answer shape could be restricted to a

the method often selects grammatically nonsensical

single token and the answer space to one of two tokens

text as the optimal prompt template. 

("positive" or "negative"), though they are unrestricted in this image. 

Dialogue-comprised Policy-gradient-based Dis-

crete Prompt Optimization (DP2O)

(Li et al., 

2023b) is perhaps the most complicated prompt en-### 2.5.1 Answer Shape

gineering technique, involving reinforcement learn-

The shape of an answer is its physical format. For

ing, a custom prompt scoring function, and conver-

example, it could be a token, span of tokens, or

sations with an LLM to construct the prompt. 

even an image or video.7 It is sometimes useful to restrict the output shape of a LLM to a single token

## 2.5 Answer Engineering

for tasks like binary classification. 

Answer engineering is the iterative process of de-

### 2.5.2 Answer Space

veloping or selecting among algorithms that extract

The space of an answer is the domain of values

precise answers from LLM outputs. To understand

that its structure may contain. This may simply be

the need for answer engineering, consider a bi-

the space of all tokens, or in a binary labeling task, 

nary classification task where the labels are "Hate

could just be two possible tokens. 

Speech" and "Not Hate Speech". The prompt template might look like this:

### 2.5.3 Answer Extractor

In cases where it is impossible to entirely control

Is this "Hate Speech" or "Not Hate Speech": the answer space (e.g. consumer-facing LLMs), or

{TEXT}

the expected answer may be located somewhere

within the model output, a rule can be defined to

When a hate speech sample is put through the

extract the final answer. This rule is often a simple

template, it might have outputs such as "It's hate

function (e.g. a regular expression), but can also

speech", "Hate Speech.", or even "Hate speech, use a separate LLM to extract the answer. 

because it uses negative language against a racial

Verbalizer

Often used in labeling tasks, a verbal-

group". This variance in response formats is diffi-

izer maps a token, span, or other type of output

cult to parse consistently; improved prompting can

to a label and vice-versa (injective) (Schick and

help, but only to a certain extent. 

Schütze, 2021). For example, if we wish for a There are three design decisions in answer en-model to predict whether a Tweet is positive or

gineering, the choice of answer space, answer

negative, we could prompt it to output either "\+" 

shape, and answer extractor (Figure 2.13). Liu

or "-" and a verbalizer would map these token se-

et al. (2023b) define the first two as necessary quences to the appropriate labels. The selection

components of answer engineering and we append

of a verbalizer constitutes a component of answer

the third. We consider answer engineering to be

engineering. 

distinct from prompt engineering, but extremely

7We use a different definition than Liu et al. (2023b) with closely related; the processes are often conducted

respect to granularity (e.g. token vs span), since the output in tandem. 

could be of a different modality. 

18

Regex

As mentioned previously, Regexes are of-

ten used to extract answers. They are usually used

to search for the first instance of a label. However, 

depending on the output format and whether CoTs

are generated, it may be better to search for the last

instance. 

Separate LLM

Sometimes outputs are so com-

plicated that regexes won't work consistently. In

this case, it can be useful to have a separate LLM

evaluate the output and extract an answer. This

separate LLM will often use an answer trigger

(Kojima et al., 2022), e.g. "The answer (Yes or No) is", to extract the answer. 

19
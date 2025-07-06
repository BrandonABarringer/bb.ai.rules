# 1. Introduction

Transformer-based LLMs are widely deployed in consumer-facing, internal, and research settings (Bommasani et al., 2021). Typically, these models rely on the user providing an input "prompt" to which the model produces an output in response. Such prompts may be textual—"Write a poem about trees."—or take other forms: images, audio, videos, or a combination thereof. The ability to prompt models, particularly prompting with natural language, makes them easy to interact with and use flexibly across a wide range of use cases. 

Knowing how to effectively structure, evaluate, and perform other tasks with prompts is essential to using these models. Empirically, better prompts lead to improved results across a wide range of tasks (Wei et al., 2022b; Liu et al., 2023b; Schulhoff, 2022). A large body of literature has grown around the use of prompting to improve results and the number of prompting techniques is rapidly increasing. 

However, as prompting is an emerging field, the use of prompts continues to be poorly understood, with only a fraction of existing terminologies and techniques being well-known among practitioners. We perform a large-scale review of prompting techniques to create a robust resource of terminology and techniques in the field. We expect this to be the first iteration of terminologies that will develop over time. We maintain an up-to-date list of terms and techniques at LearnPrompting.org. 

## Scope of Study

We create a broad directory of prompting techniques, that can be quickly understood and easily implemented for rapid experimentation by developers and researchers. To this end, we limit our study to focus on prefix prompts (Shin et al., 2020a) rather than cloze prompts (Petroni et al., 2019; Cui et al., 2021), because modern LLM transformer architectures widely employ prefix prompts and provide robust support for both developers and researchers (Brown et al., 2020; Google, 2023; Touvron et al., 2023). Additionally, we refined our focus to hard (discrete) prompts rather than soft (continuous) prompts and leave out papers that make use of techniques using gradient-based updates (i.e. fine-tuning). Hard prompts contain only tokens (vectors) that correspond to words in the model's vocabulary, while soft prompts may contain tokens that have no corresponding word in the vocabulary. 

Finally, we only study task-agnostic techniques. These decisions keep the work approachable to less technical readers and maintain a manageable scope. 

## Sections Overview

We conducted a machine-assisted systematic review grounded in the PRISMA process (Page et al., 2021) (Section 2.1) to identify 58 different text-based prompting techniques, from which we create a taxonomy with a robust terminology of prompting terms (Section 1.2). 

Our goal is to provide a roadmap for the community when considering which prompting techniques to use (Figure 1.1). While much literature on prompting focuses on English-only settings, we also discuss multilingual techniques (Section 3.1). Given the rapid growth in multimodal prompting, where prompts may include media such as images, we also expand our scope to multimodal techniques (Section 3.2). Many multilingual and multimodal prompting techniques are direct extensions of English text-only prompting techniques. 

As prompting techniques grow more complex, they have begun to incorporate external tools, such as Internet browsing and calculators. We use the term "agents" to describe these types of prompting techniques (Section 4.1). 

It is important to understand how to evaluate the outputs of agents and prompting techniques to ensure accuracy and avoid hallucinations. Thus, we discuss ways of evaluating these outputs (Section 4.2). We also discuss security (Section 5.1) and safety measures (Section 5.2) for designing prompts that reduce the risk of harm to companies and users. 

Finally, we apply prompting techniques in two case studies (Section 6.1). In the first, we test a range of prompting techniques against the commonly used benchmark MMLU (Hendrycks et al., 2021). In the second, we explore in detail an example of manual prompt engineering on a significant, real-world use case, identifying signals of frantic hopelessness–a top indicator of suicidal crisis–in the text of individuals seeking support (Schuck et al., 2019a). We conclude with a discussion of the nature of prompting and its recent development (Section 8). 

## 1.1 What is a Prompt?

A prompt is an input to a Generative AI model, that is used to guide its output (Meskó, 2023; White et al., 2023; Heston and Khun, 2023; Hadi et al., 2023; Brown et al., 2020). Prompts may consist of text, image, sound, or other media. Some examples of prompts include the text, "write a three paragraph email for a marketing campaign for an accounting firm", a photograph of a piece of paper with the words "what is 10*179" written on it, or a recording of an online meeting, with the instructions "summarize this". Prompts usually have some text component, but this may change as non-text modalities become more common. 

### Prompt Template

Prompts are often constructed via a prompt template (Shin et al., 2020b). A prompt template is a function that contains one or more variables which will be replaced by some media (usually text) to create a prompt. This prompt can then be considered to be an instance of the template. 

Consider applying prompting to the task of binary classification of tweets. Here is an initial prompt template that can be used to classify inputs. 

```
Classify the tweet as positive or negative:
{TWEET}
```

Each tweet in the dataset would be inserted into a separate instance of the template and the resulting prompt would be given to a LLM for inference. 

## 1.2 Terminology

### 1.2.1 Components of a Prompt

There are a variety of common components included in a prompt. We summarize the most commonly used components and discuss how they fit into prompts (Figure 1.3). 

**Directive** - Many prompts issue a directive in the form of an instruction or question.[1] This is the core intent of the prompt, sometimes simply called the "intent". For example, here is an instance of a prompt with a single instruction:

```
Tell me five good books to read.
```

Directives can also be implicit, as in this one-shot case, where the directive is to perform English to Spanish translation:

```
Night: Noche
Morning:
```

**Examples** - Examples, also known as exemplars or shots, act as demonstrations that guide the GenAI to accomplish a task. The above prompt is a One-Shot (i.e. one example) prompt. 

**Output Formatting** - It is often desirable for the GenAI to output information in certain formats, for example, CSV, Markdown, XML, or even custom formats(Xia et al., 2024). Structuring outputs may reduce performance on some tasks (Tam et al., 2024). However, Kurt (2024) point out various flaws in Tam et al. (2024) and show that structuring outputs may actually improve performance. Here is an example of how you might format a prompt to output information as a CSV:

```
{PARAGRAPH}
Summarize this into a CSV.
```

**Style Instructions** - Style instructions are a type of output formatting used to modify the output stylistically rather than structurally (Section 2.2.1.3). For example:

```
Write a clear and curt paragraph about llamas.
```

**Role** - A Role, also known as a persona (Schmidt et al., 2023; Wang et al., 2023l), is a frequently discussed component that can improve writing and style text (Section 2.2.1.3). For example:

```
Pretend you are a shepherd and write a limerick about llamas.
```

**Additional Information** - It is often necessary to include additional information in the prompt. For example, if the directive is to write an email, you might include information such as your name and position so the GenAI can properly sign the email. Additional Information is sometimes called 'context', though we discourage the use of this term as it is overloaded with other meanings in the prompting space[2].

### 1.2.2 Prompting Terms

Terminology within the prompting literature is rapidly developing. As it stands, there are many poorly understood definitions (e.g. prompt, prompt engineering) and conflicting ones (e.g. role prompt vs persona prompt). The lack of a consistent vocabulary hampers the community's ability to clearly describe the various prompting techniques in use. We provide a robust vocabulary of terms used in the prompting community (Figure 1.3).[3] Less frequent terms are left to Appendix A.2. In order to accurately define frequently-used terms like prompt and prompt engineering, we integrate many definitions (Appendix A.1) to derive representative definitions.

**Prompting** - Prompting is the process of providing a prompt to a GenAI, which then generates a response. For example, the action of sending a chunk of text or uploading an image constitutes prompting.

**Prompt Chain** - A prompt chain (activity: prompt chaining) consists of two or more prompt templates used in succession. The output of the prompt generated by the first prompt template is used to parameterize the second template, continuing until all templates are exhausted (Wu et al., 2022).

**Prompting Technique** - A prompting technique is a blueprint that describes how to structure a prompt, prompts, or dynamic sequencing of multiple prompts. A prompting technique may incorporate conditional or branching logic, parallelism, or other architectural considerations spanning multiple prompts.

**Prompt Engineering** - Prompt engineering is the iterative process of developing a prompt by modifying or changing the prompting technique that you are using (Figure 1.4).

**Prompt Engineering Technique** - A prompt engineering technique is a strategy for iterating on a prompt to improve it. In literature, this will often be automated techniques (Deng et al., 2022), but in consumer settings, users often perform prompt engineering manually, without any assistive tooling.

**Exemplar** - Exemplars are examples of a task being completed that are shown to a model in a prompt (Brown et al., 2020).

## 1.3 A Short History of Prompts

The idea of using natural language prefixes, or prompts, to elicit language model behaviors and responses originated before the GPT-3 and ChatGPT era. GPT-2 (Radford et al., 2019a) makes use of prompts and they appear to be first used in the context of Generative AI by Fan et al. (2018). However, the concept of prompts was preceded by related concepts such as control codes (Pfaff, 1979; Poplack, 1980; Keskar et al., 2019) and writing prompts in literature.

The term Prompt Engineering appears to have come into existence more recently from Radford et al. (2021) then slightly later from Reynolds and McDonell (2021).

However, various papers perform prompt engineering without naming the term (Wallace et al., 2019; Shin et al., 2020a), including Schick and Schütze (2020a,b); Gao et al. (2021) for non-autoregressive language models.

Some of the first works on prompting define a prompt slightly differently to how it is currently used. For example, consider the following prompt from Brown et al. (2020):

```
Translate English to French:
llama
```

Brown et al. (2020) consider the word "llama" to be the prompt, while "Translate English to French:" is the "task description". More recent papers, including this one, refer to the entire string passed to the LLM as the prompt.

---

[1] "Directives", from Searle (1969), are a type of speech act intended to encourage an action, and have been invoked in models of human-computer dialogue Morelli et al. (1991).

[2] e.g. the context is the tokens processed by the LLM in a forward pass

[3] By robust, we mean that it covers most existing commonly used terms in the field.
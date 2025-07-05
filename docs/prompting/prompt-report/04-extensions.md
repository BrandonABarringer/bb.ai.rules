# 4 Extensions of Prompting

The techniques we have discussed thus far can be extremely complicated, incorporating many steps and iterations. However, we can take prompting further by adding access to external tools (agents) and complex evaluation algorithms to judge the validity of LLM outputs.

## 4.1 Agents

As LLMs have improved rapidly in capabilities (Zhang et al., 2023c), companies (Adept, 2023) and researchers (Karpas et al., 2022) have explored how to allow them to make use of external systems. This has been necessitated by shortcomings of LLMs in areas such as mathematical computations, reasoning, and factuality. This has driven significant innovations in prompting techniques; these systems are often driven by prompts and prompt chains, which are heavily engineered to allow for agent-like behaviour (Figure 4.1).

**Definition of Agent**: In the context of GenAI, we define agents to be GenAI systems that serve a user's goals via actions that engage with systems outside the GenAI itself. This GenAI is usually a LLM. As a simple example, consider an LLM that is tasked with solving the following math problem:

*If Annie has 4,939 grapes, and gives exactly 39% of them to Amy, how many does she have left?*

If properly prompted, the LLM could output the string CALC(4,939*.39). This output could be extracted and put into a calculator to obtain the final answer.

This is an example of an agent: the LLM outputs text which then uses a downstream tool. Agent LLMs may involve a single external system (as above), or they may need to solve the problem of routing, to choose which external system to use. Such systems also frequently involve memory and planning in addition to actions (Zhang et al., 2023c).

Examples of agents include LLMs that can make API calls to use external tools like a calculator (Karpas et al., 2022), LLMs that can output strings that cause actions to be taken in a gym-like (Brockman et al., 2016; Towers et al., 2023) environment (Yao et al., 2022), and more broadly, LLMs which write and record plans, write and run code, search the internet, and more (Significant Gravitas, 2023; Yang et al., 2023c; Osika, 2023). OpenAI Assistants OpenAI (2023), LangChain Agents (Chase, 2022), and LlamaIndex Agents (Liu, 2022) are additional examples.

### 4.1.1 Tool Use Agents

Tool use is a critical component for GenAI agents. Both symbolic (e.g. calculator, code interpreter) and neural (e.g. a separate LLM) external tools are commonly used. Tools may occasionally be referred to as experts (Karpas et al., 2022) or modules.

**Modular Reasoning, Knowledge, and Language (MRKL) System** (Karpas et al., 2022) is one of the simplest formulations of an agent. It contains a LLM router providing access to multiple tools. The router can make multiple calls to get information such as weather or the current date. It then combines this information to generate a final response. Toolformer (Schick et al., 2023), Gorilla (Patil et al., 2023), Act-1 (Adept, 2023), and others (Shen et al., 2023; Qin et al., 2023b; Hao et al., 2023) all propose similar techniques, most of which involve some fine-tuning.

**Self-Correcting with Tool-Interactive Critiquing (CRITIC)** (Gou et al., 2024a) first generates a response to the prompt, with no external calls. Then, the same LLM criticizes this response for possible errors. Finally, it uses tools (e.g. Internet search or a code interpreter) accordingly to verify or amend parts of the response.

### 4.1.2 Code-Generation Agents

Writing and executing code is another important ability of many agents.

**Program-aided Language Model (PAL)** (Gao et al., 2023b) translates a problem directly into code, which is sent to a Python interpreter to generate an answer.

**Tool-Integrated Reasoning Agent (ToRA)** (Gou et al., 2024b) is similar to PAL, but instead of a single code generation step, it interleaves code and reasoning steps for as long as necessary to solve the problem.

**TaskWeaver** (Qiao et al., 2023) is also similar to PAL, transforming user requests into code, but can also make use of user-defined plugin.

### 4.1.3 Observation-Based Agents

Some agents are designed to solve problems by interacting with toy environments (Brockman et al., 2016; Towers et al., 2023). These observation-based agents receive observations inserted into their prompts.

**Reasoning and Acting (ReAct)** (Yao et al. (2022)) generates a thought, takes an action, and receives an observation (and repeats this process) when given a problem to solve. All of this information is inserted into the prompt so it has a memory of past thoughts, actions, and observations.

**Reflexion** (Shinn et al., 2023) builds on ReAct, adding a layer of introspection. It obtains a trajectory of actions and observations, then is given an evaluation of success/failure. Then, it generates a reflection on what it did and what went wrong. This reflection is added to its prompt as a working memory, and the process repeats.

#### 4.1.3.1 Lifelong Learning Agents

Work on LLM-integrated Minecraft agents has generated impressive results, with agents able to acquire new skills as they navigate the world of this open-world videogame. We view these agents not merely as applications of agent techniques to Minecraft, but rather novel agent frameworks which can be explored in real world tasks that require lifelong learning.

**Voyager** (Wang et al., 2023a) is composed of three parts. First, it proposes tasks for itself to complete in order to learn more about the world. Second, it generates code to execute these actions. Finally, it saves these actions to be retrieved later when useful, as part of a long-term memory system. This system could be applied to real world tasks where an agent needs to explore and interact with a tool or website (e.g. penetration testing, usability testing).

**Ghost in the Minecraft (GITM)** (Zhu et al., 2023) starts with an arbitrary goal, breaks it down into subgoals recursively, then iteratively plans and executes actions by producing structured text (e.g. "equip(sword)") rather than writing code. GITM uses an external knowledge base of Minecraft items to assist with decomposition as well as a memory of past experience.

### 4.1.4 Retrieval Augmented Generation (RAG)

In the context of GenAI agents, RAG is a paradigm in which information is retrieved from an external source and inserted into the prompt. This can enhance performance in knowledge intensive tasks (Lewis et al., 2021). When retrieval itself is used as an external tool, RAG systems are considered to be agents.

**Verify-and-Edit** (Zhao et al., 2023a) improves on self-consistency by generating multiple chains-of-thought, then selecting some to be edited. They do this by retrieving relevant (external) information to the CoTs, and allowing the LLM to augment them accordingly.

**Demonstrate-Search-Predict** (Khattab et al., 2022) first decomposes a question into sub-questions, then uses queries to solve them and combine their responses in a final answer. It uses few-shot prompting to decompose the problem and combine responses.

**Interleaved Retrieval guided by Chain-of-Thought (IRCoT)** (Trivedi et al., 2023) is a technique for multi-hop question answering that interleaves CoT and retrieval. IRCoT leverages CoT to guide which documents to retrieve and retrieval to help plan the reasoning steps of CoT.

**Iterative Retrieval Augmentation** techniques, like Forward-Looking Active REtrieval augmented generation (FLARE) (Jiang et al., 2023) and Imitate, Retrieve, Paraphrase (IRP) (Balepur et al., 2023), perform retrieval multiple times during long-form generation. Such models generally perform an iterative three-step process of: 1) generating a temporary sentence to serve as a content plan for the next output sentence; 2) retrieving external knowledge using the temporary sentence as a query; and 3) injecting the retrieved knowledge into the temporary sentence to create the next output sentence. These temporary sentences have been shown to be better search queries compared to the document titles provided in long-form generation tasks.

## 4.2 Evaluation

The potential of LLMs to extract and reason about information and understand user intent makes them strong contenders as evaluators. For example, it is possible to prompt a LLM to evaluate the quality of an essay or even a previous LLM output according to some metrics defined in the prompt. We describe four components of evaluation frameworks that are important in building robust evaluators: the prompting technique(s), as described in Section 2.2, the output format of the evaluation, the framework of the evaluation pipeline, and some other methodological design decisions (Figure 4.2).

### 4.2.1 Prompting Techniques

The prompting technique used in the evaluator prompt (e.g. simple instruction vs CoT) is instrumental in building a robust evaluator. Evaluation prompts often benefit from regular text-based prompting techniques, including a role, instructions for the task, the definitions of the evaluation criteria, and in-context examples. Find a full list of techniques in Appendix A.6.

**In-Context Learning** is frequently used in evaluation prompts, much in the same way it is used in other applications (Dubois et al., 2023; Kocmi and Federmann, 2023a; Brown et al., 2020).

**Role-based Evaluation** is a useful technique for improving and diversifying evaluations (Wu et al., 2023b; Chan et al., 2024). By creating prompts with the same instructions for evaluation, but different roles, it is possible to effectively generate diverse evaluations. Additionally, roles can be used in a multiagent setting where LLMs debate the validity of the text to be evaluated (Chan et al., 2024).

**Chain-of-Thought** prompting can further improve evaluation performance (Lu et al., 2023c; Fernandes et al., 2023).

**Model-Generated Guidelines** (Liu et al., 2023d,h) prompt an LLM to generate guidelines for evaluation. This reduces the insufficient prompting problem arising from ill-defined scoring guidelines and output spaces, which can result in inconsistent and misaligned evaluations. Liu et al. (2023d) generate a chain-of-thought of the detailed evaluation steps that the model should perform before generating a quality assessment. Liu et al. (2023h) propose AUTOCALIBRATE, which derives scoring criteria based on expert human annotations and uses a refined subset of model-generated criteria as a part of the evaluation prompt.

### 4.2.2 Output Format

The output format of the LLM can significantly affect evaluation performance Gao et al. (2023c).

**Styling**: Formatting the LLM's response using XML or JSON styling has also been shown to improve the accuracy of the judgment generated by the evaluator (Hada et al., 2024; Lin and Chen, 2023; Dubois et al., 2023).

**Linear Scale**: A very simple output format is a linear scale (e.g. 1-5). Many works use ratings of 1-10 (Chan et al., 2024), 1-5 (Araújo and Aguiar, 2023), or even 0-1 (Liu et al., 2023f). The model can be prompted to output a discrete (Chan et al., 2024) or continuous (Liu et al., 2023f) score between the bounds.

*Example:*
```
Score the following story on a scale of 1-5 from well to poorly written:
{INPUT}
```

**Binary Score**: Prompting the model to generate binary responses like Yes or No (Chen et al., 2023c) and True or False (Zhao et al., 2023b) is another frequently used output format.

*Example:*
```
Is the following story well written at a high-school level (yes/no)?:
{INPUT}
```

**Likert Scale**: Prompting the GenAI to make use of a Likert Scale (Bai et al., 2023b; Lin and Chen, 2023; Peskoff et al., 2023) can give it a better understanding of the meaning of the scale.

*Example:*
```
Score the following story according to the following scale:
Poor
Acceptable
Good
Very Good
Incredible
{INPUT}
```

### 4.2.3 Prompting Frameworks

**LLM-EVAL** (Lin and Chen, 2023) is one of the simplest evaluation frameworks. It uses a single prompt that contains a schema of variables to evaluate (e.g. grammar, relevance, etc.), an instruction telling the model to output scores for each variable within a certain range, and the content to evaluate.

**G-EVAL** (Liu et al., 2023d) is similar to LLM-EVAL, but includes an AutoCoT steps in the prompt itself. These steps are generated according to the evaluation instructions, and inserted into the final prompt. These weight answers according to token probabilities.

**ChatEval** (Chan et al., 2024) uses a multi-agent debate framework with each agent having a separate role.

### 4.2.4 Other Methodologies

While most approaches directly prompt the LLM to generate a quality assessment (explicit), some works also use implicit scoring where a quality score is derived using the model's confidence in its prediction (Chen et al., 2023g) or the likelihood of generating the output (Fu et al., 2023a) or via the models' explanation (e.g. count the number of errors as in Fernandes et al. (2023); Kocmi and Federmann (2023a)) or via evaluation on proxy tasks (factual inconsistency via entailment as in Luo et al. (2023)).

**Batch Prompting**: For improving compute and cost efficiency, some works employ batch prompting for evaluation where multiple instances are evaluated at once (Lu et al., 2023c; Araújo and Aguiar, 2023; Dubois et al., 2023) or the same instance is evaluated under different criteria or roles (Wu et al., 2023b; Lin and Chen, 2023). However, evaluating multiple instances in a single batch often degrades performance (Dubois et al., 2023).

**Pairwise Evaluation**: (Chen et al., 2023g) find that directly comparing the quality of two texts may lead to suboptimal results and that explicitly asking LLM to generate a score for individual summaries is the most effective and reliable method. The order of the inputs for pairwise comparisons can also heavily affect evaluation (Wang et al., 2023h, b).

---

*Note: This section does not describe how to benchmark LLMs, but rather how to use them as evaluators.*

*Footnotes:*
- We do not cover the notion of independently-acting AI, i.e. systems that in any sense have their own goals
- This ability may be considered a tool (i.e. code interpreter)
- Disambiguation: there is no relation to making a forward pass with multiple prompts in parallel. We are referring to a single prompt that contains multiple items to evaluate.
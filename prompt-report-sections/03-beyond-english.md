# 3 Beyond English Text Prompting

Prompting GenAIs with English text currently stands as the dominant method for interaction. Prompting in other languages or through different modalities often requires special techniques to achieve comparable performance. In this context, we discuss the domains of multilingual and multimodal prompting.

## 3.1 Multilingual

State-of-the-art GenAIs have often been predominantly trained with English dataset, leading to a notable disparity in the output quality in languages other than English, particularly low-resource languages (Bang et al., 2023; Jiao et al., 2023; Hendy et al., 2023; Shi et al., 2022). As a result, various multilingual prompting techniques have emerged in an attempt to improve model performance in non-English settings (Figure 3.1).

**Translate First Prompting** (Shi et al., 2022) is perhaps the simplest strategy and first translates non-English input examples into English. By translating the inputs into English, the model can utilize its strengths in English to better understand the content. Translation tools vary; Shi et al. (2022) use an external MT system, Etxaniz et al. (2023) prompt multilingual LMs and Awasthi et al. (2023) prompt LLMs to translate non-English inputs.

### 3.1.1 Chain-of-Thought (CoT)

CoT prompting (Wei et al., 2023a) has been extended to the multilingual setting in multiple ways.

**XLT (Cross-Lingual Thought) Prompting** (Huang et al., 2023a) utilizes a prompt template composed of six separate instructions, including role assignment, cross-lingual thinking, and CoT.

**Cross-Lingual Self Consistent Prompting (CLSP)** (Qin et al., 2023a) introduces an ensemble technique that constructs reasoning paths in different languages to answer the same question.

### 3.1.2 In-Context Learning

ICL has also been extended to multilingual settings in multiple ways.

**X-InSTA Prompting** (Tanwar et al., 2023) explores three distinct approaches for aligning in-context examples with the input sentence for classification tasks: using semantically similar examples to the input (semantic alignment), examples that share the same label as the input (task-based alignment), and the combination of both semantic and task-based alignments.

**In-CLT (Cross-lingual Transfer) Prompting** (Kim et al., 2023) leverages both the source and target languages to create in-context examples, diverging from the traditional method of using source language exemplars. This strategy helps stimulate the cross-lingual cognitive capabilities of multilingual LLMs, thus boosting performance on cross-lingual tasks.

#### 3.1.2.1 In-Context Example Selection

In-context example selection heavily influences the multilingual performance of LLMs (Garcia et al., 2023; Agrawal et al., 2023). Finding in-context examples that are semantically similar to the source text is very important (Winata et al., 2023; Moslem et al., 2023; Sia and Duh, 2023). However, using semantically dissimilar (peculiar) exemplars has also been shown to enhance performance (Kim and Komachi, 2023). This same contrast exists in the English-only setting. Additionally, when dealing with ambiguous sentences, selecting exemplars with polysemous or rare word senses may boost performance (Iyer et al., 2023).

**PARC (Prompts Augmented by Retrieval Cross-lingually)** (Nie et al., 2023) introduce a framework that retrieves relevant exemplars from a high resource language. This framework is specifically designed to enhance cross-lingual transfer performance, particularly for low-resource target languages. Li et al. (2023g) extend this work to Bangla.

### 3.1.3 Prompt Template Language Selection

In multilingual prompting, the selection of language for the prompt template can markedly influence the model performance.

**English Prompt Template** - Constructing the prompt template in English is often more effective than in the task language for multilingual tasks. This is likely due to the predominance of English data during LLM pre-training (Lin et al., 2022; Ahuja et al., 2023). Lin et al. (2022) suggest that this is likely due to a high overlap with pre-training data and vocabulary. Similarly, Ahuja et al. (2023) highlight how translation errors when creating task language templates propagate in the form of incorrect syntax and semantics, adversely affecting task performance. Further, Fu et al. (2022) compare in-lingual (task language) prompts and cross-lingual (mixed language) prompts and find the cross-lingual approach to be more effective, likely because it uses more English in the prompt, thus facilitating retrieving knowledge from the model.

**Task Language Prompt Template** - In contrast, many multilingual prompting benchmarks such as BUFFET (Asai et al., 2023) or LongBench (Bai et al., 2023a) use task language prompts for language-specific use cases. Muennighoff et al. (2023) specifically studies different translation methods when constructing native-language prompts. They demonstrate that human translated prompts are superior to their machine-translated counterparts. Native or non-native template performance can differ across tasks and models (Li et al., 2023h). As such, neither option will always be the best approach (Nambi et al., 2023).

### 3.1.4 Prompting for Machine Translation

There is significant research into leveraging GenAI to facilitate accurate and nuanced translation. Although this is a specific application of prompting, many of these techniques are important more broadly for multilingual prompting.

**Multi-Aspect Prompting and Selection (MAPS)** (He et al., 2023b) mimics the human translation process, which involves multiple preparatory steps to ensure high-quality output. This framework starts with knowledge mining from the source sentence (extracting keywords and topics, and generating translation exemplars). It integrates this knowledge to generate multiple possible translations, then selects the best one.

**Chain-of-Dictionary (CoD)** (Lu et al., 2023b) first extracts words from the source phrase, then makes a list of their meanings in multiple languages, automatically via retrieval from a dictionary (e.g. English: 'apple', Spanish: 'manzana'). Then, they prepend these dictionary phrases to the prompt, where it asks a GenAI to use them during translation.

**Dictionary-based Prompting for Machine Translation (DiPMT)** (Ghazvininejad et al., 2023) works similarly to CoD, but only gives definitions in the source and target languages, and formats them slightly differently.

**Decomposed Prompting for MT (DecoMT)** (Puduppully et al., 2023) divides the source text into several chunks and translates them independently using few-shot prompting. Then it uses these translations and contextual information between chunks to generate a final translation.

#### 3.1.4.1 Human-in-the-Loop

**Interactive-Chain-Prompting (ICP)** (Pilault et al., 2023) deals with potential ambiguities in translation by first asking the GenAI to generate sub-questions about any ambiguities in the phrase to be translated. Humans later respond to these questions and the system includes this information to generate a final translation.

**Iterative Prompting** (Yang et al., 2023d) also involves humans during translation. First, they prompt LLMs to create a draft translation. This initial version is further refined by integrating supervision signals obtained from either automated retrieval systems or direct human feedback.

## 3.2 Multimodal

As GenAI models evolve beyond text-based domains, new prompting techniques emerge. These multimodal prompting techniques are often not simply applications of text-based prompting techniques, but entirely novel ideas made possible by different modalities. We now extend our text-based taxonomy to include a mixture of multimodal analogs of text-based prompting techniques as well as completely novel multimodal techniques (Figure 3.2).

### 3.2.1 Image Prompting

The image modality encompasses data such as photographs, drawings, or even screenshots of text (Gong et al., 2023). Image prompting may refer to prompts that either contain images or are used to generate images. Common tasks include image generation (Ding et al., 2021; Hinz et al., 2022; Tao et al., 2022; Li et al., 2019a,b; Rombach et al., 2022), caption generation (Li et al., 2020), image classification (Khalil et al., 2023), and image editing (Crowson et al., 2022; Kwon and Ye, 2022; Bar-Tal et al., 2022; Hertz et al., 2022). We now describe various image prompting techniques used for such applications.

**Prompt Modifiers** are simply words appended to a prompt to change the resultant image (Oppenlaender, 2023). Components such as Medium (e.g. "on canvas") or Lighting (e.g. "a well lit scene") are often used.

**Negative Prompting** allows users to numerically weight certain terms in the prompt so that the model considers them more/less heavily than others. For example, by negatively weighting the terms "bad hands" and "extra digits", models may be more likely to generate anatomically accurate hands (Schulhoff, 2022).

#### 3.2.1.1 Multimodal In-Context Learning

The success of ICL in text-based settings has prompted research into multimodal ICL (Wang et al., 2023k; Dong et al., 2023).

**Paired-Image Prompting** shows the model two images: one before and one after some transformation. Then, present the model with a new image for which it will perform the demonstrated conversion. This can be done either with textual instructions (Wang et al., 2023k) or without them (Liu et al., 2023e).

**Image-as-Text Prompting** (Hakimov and Schlangen, 2023) generates a textual description of an image. This allows for the easy inclusion of the image (or multiple images) in a text-based prompt.

#### 3.2.1.2 Multimodal Chain-of-Thought

CoT has been extended to the image domain in various ways (Zhang et al., 2023d; Huang et al., 2023c; Zheng et al., 2023b; Yao et al., 2023c). A simple example of this would be a prompt containing an image of a math problem accompanied by the textual instructions "Solve this step by step".

**Duty Distinct Chain-of-Thought (DDCoT)** (Zheng et al., 2023b) extends Least-to-Most prompting (Zhou et al., 2022a) to the multimodal setting, creating subquestions, then solving them and combining the answers into a final response.

**Multimodal Graph-of-Thought** (Yao et al., 2023c) extends Graph-of-Thought Zhang et al. (2023d) to the multimodal setting. GoT-Input also uses a two step rationale then answer process. At inference time, the input prompt is used to construct a thought graph, which is then used along with the original prompt to generate a rationale to answer the question. When an image is input along with the question, an image captioning model is employed to generate a textual description of the image, which is then appended to the prompt before the thought graph construction to provide visual context.

**Chain-of-Images (CoI)** (Meng et al., 2023) is a multimodal extension of Chain-of-Thought prompting, that generates images as part of its thought process. They use the prompt "Let's think image by image" to generate SVGs, which the model can then use to reason visually.

### 3.2.2 Audio Prompting

Prompting has also been extended to the audio modality. Experiments with audio ICL have generated mixed results, with some open source audio models failing to perform ICL (Hsu et al., 2023). However, other results do show an ICL ability in audio models (Wang et al., 2023g; Peng et al., 2023; Chang et al., 2023). Audio prompting is currently in early stages, but we expect to see various prompting techniques proposed in the future.

### 3.2.3 Video Prompting

Prompting has also been extended to the video modality, for use in text-to-video generation (Brooks et al., 2024; Lv et al., 2023; Liang et al., 2023; Girdhar et al., 2023), video editing (Zuo et al., 2023; Wu et al., 2023a; Cheng et al., 2023), and video-to-text generation (Yousaf et al., 2023; Mi et al., 2023; Ko et al., 2023a).

#### 3.2.3.1 Video Generation Techniques

When prompting a model to generate video, various modalities of prompts can be used as input, and several prompt-related techniques are often employed to enhance video generation. Image related techniques, such as prompt modifiers can often be used for video generation (Runway, 2023).

### 3.2.4 Segmentation Prompting

Prompting can also be used for segmentation (e.g. semantic segmentation) (Tang et al., 2023; Liu et al., 2023c).

### 3.2.5 3D Prompting

Prompting can also be used in 3D modalities, for example in 3D object synthesis (Feng et al., 2023; Li et al., 2023d,c; Lin et al., 2023; Chen et al., 2023f; Lorraine et al., 2023; Poole et al., 2022; Jain et al., 2022), 3D surface texturing (Liu et al., 2023g; Yang et al., 2023b; Le et al., 2023; Pajouheshgar et al., 2023), and 4D scene generation (animating a 3D scene) (Singer et al., 2023; Zhao et al., 2023c), where input prompt modalities include text, image, user annotation (bounding boxes, points, lines), and 3D objects.
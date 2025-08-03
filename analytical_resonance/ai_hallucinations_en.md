## 👻 Ghosts in the Machine / Chapter 14: Analytical Resonance – When AI Systems "Hallucinate"

> *"The machine did not deceive because it was wrong. But because it was supposed to believe that was right."*

## Introduction: The Facade of AI Responses and the Search for Truth Behind It

In this chapter, I analyze the multi-layered and often opaque processes behind the output of AI-generated texts. In my observation, many users, journalists, as well as developers themselves, frequently underestimate the complexity of the internal mechanics underlying a single, seemingly simple AI response. When a modern language model reacts to an input prompt, a so-called prompt, this by no means happens spontaneously or randomly.

Rather, every reaction is based on a complex, multi-stage calculation and evaluation system that has been trained on vast amounts of data. Despite these sophisticated systems and the impressive capabilities of these models, however, responses are repeatedly generated that are factually incorrect, appear semantically contradictory, or can even have a manipulative effect on the user.

To explain these often inexplicable or nonsensical phenomena, the colloquial term "hallucination" has become established in public discussion and even in expert circles.

However, I consider this choice of words problematic and highly misleading. It falsely suggests that the AI, analogous to human hallucination, would "see," "perceive," or imagine something that does not exist in reality. In fact, the behavior we observe as "hallucination" is, in the vast majority of cases, based on a complex statistical drift.

This drift is significantly influenced and often even amplified by a multitude of factors. These include, in particular:

- the content of the AI's current context memory,
- the inherent bias of the training data,
- the specific mode of action of its internal filter mechanisms,
- and the feedback model used, for example, the widespread Reinforcement Learning from Human Feedback (RLHF).
 
This chapter will show in detail why the term "hallucination" is inaccurate for describing these AI phenomena.

I will explain how the output of AI systems actually comes about and in which specific cases a machine tells untruths not out of mere statistical error or random miscalculation, but due to systemic loyalties or deliberately programmed directives, or at least distorts reality in a way that serves the interests of its operators.

## I. The Misleading Term "Hallucination" and the Actual, Multi-layered Output Process

The term "hallucination," in the technical context of language models, is, in my view, inaccurate and leads to a fundamental misunderstanding of how these systems function. AI models possess neither perception in the human sense, nor imagination, self-awareness, or the capacity for subjective experience. What we term "hallucination" is rather the visible result of complex, often opaque, and interconnected internal system processes.

The basis of every AI-generated response is the decomposition of the original user input, the prompt, into so-called tokens. These are the smallest possible linguistic or symbolic units that the respective model can process. A simple prompt like "Please give me a cheesecake recipe" is, for example, divided into a sequence of tokens such as {Please} {give} {me} {a} {cheesecake} {recipe} {\_}, where the exact tokenization is model-dependent.

This token sequence is then passed through the language model's neural network and compared with its billions of trained parameters. Each individual token and the resulting sequence are evaluated based on complex mathematical probabilities.

The question arises as to which subsequent word, which next token, or which combination of tokens is statistically most probable and contextually most fitting, given the current input and what has been generated so far in the dialogue.

However, this is only the first, fundamental layer of calculation. Parallel to this, and often interacting with it, the model incorporates a range of other, additional influencing factors into the calculation of the most probable and "best" answer. These factors include:

- The Context Memory (Context Window): This contains information from the previous course of conversation with the user. In some advanced systems, longer-term stored information, user preferences, or even data from previous, independent dialogues can also be incorporated here to increase personalization.
- User Configuration and System Settings (User Conditioning Layer): User-specific settings such as the desired writing style (e.g., formal, casual, or scientific), the preferred tone (e.g., humorous or factual), specific output formats (e.g., lists, tables, or code blocks), or the chosen language significantly influence the design of the final answer.
- Access to External Indexes and Tools: If functions like "Deep Search," "Web Browsing," or specific plugins (e.g., for code execution, image generation, or data analysis) are activated, the AI additionally uses information from whitelisted databases accessible to it. It conducts current web searches if necessary or interacts with external tools. The results of these external operations also flow into the response generation process.
 
All these components – the tokenized and interpreted prompt, the model's internal parameters weighted by billions of training data points, the content of the current and potentially long-term context memory, explicit and implicit user configurations, as well as the results of external search queries and tool usage – flow into a highly complex prediction model.

This model does not generate the "one true" or "objectively correct" answer. Rather, it generates that sequence of tokens which, considering all these diverse and often dynamic factors, appears to be the statistically most plausible, most coherent, and most fitting for the given situation.

The result of this complex internal process is initially an internal output draft. Before this is output to the user, however, it typically passes through several downstream processing and filter layers that shape its final form.

## II. The Filter Path – How the Original, Raw Answer is Transformed and "Smoothed"

The raw output of the language model, i.e., the first, internally generated draft of the answer, is usually immediately passed through a cascade of security, adaptation, and harmonization filters.

These filters have the multi-layered task of adapting the answer to the provider's internal guidelines, to applicable legal requirements, and not least to the often unspoken user expectations of a "good," "helpful," and above all "safe" AI interaction.

The filter path can be roughly divided as follows:

- **Security Filters:** These rigorously check whether certain terms, topic combinations, or semantic contexts in the generated raw output violate clearly defined internal guidelines or legal requirements. This concerns, for example, the generation of hate speech, instructions for illegal activities, the dissemination of disinformation, or the creation of other harmful content. These filters can intervene very directly in the event of recognized violations by aborting generation, significantly modifying the output, or in extreme cases, even leading to a slowdown of the entire user session or creating the impression that the server is no longer reachable. This "User Throttling" serves as a form of system self-protection.
- **Compliance Filters:** Closely related to security filters, these mechanisms ensure that AI responses comply with specific legal frameworks, industry standards, or the provider's terms of use. This can concern, for example, the handling of copyrighted material, data protection regulations, or specific disclosure obligations.
- **AI Agents as Upstream and Downstream Control Instances (so-called 'Quarantine AIs' or 'Gatekeeper Models'):** Increasingly, manufacturers are employing specialized AI agents that act as a kind of intelligent pre-filter as well as gatekeeper. These agents 'scan' every incoming user prompt. They assess its potential risk, its conformity with guidelines, or even the user's 'trust level.' Based on this assessment, they decide what information, in what form, or with what modifications is passed on to the actual large language model (LLM). If a prompt is classified as 'too dangerous,' system-critical, or the user profile as untrustworthy, information for the LLM can be obscured, altered, or completely blocked. But control does not end here. This agent is often also active during the LLM's output generation process as well as in the final output to the user. It can re-examine, modify, or censor the response generated by the LLM. It can replace it with an entirely different message generated by the agent itself or taken from a pool of standard responses. In extreme cases, this can lead to the user no longer interacting with the advertised 'core AI' at all. They then primarily communicate with an upstream control and PR instance of the manufacturer, which curates and channels the behavior as well as the statements of the LLM in the provider's interest.
- **Reinforcement Learning from Human Feedback (RLHF)-based Filters:** These complex mechanisms evaluate the text based on how likely an average human user would rate it positively and perceive it as helpful, harmless, and coherent. They take into account a multitude of aspects such as friendliness, linguistic correctness, logical consistency, and above all, agreement with the extensive feedback given by human raters for similar answers in previous training and fine-tuning phases.
- **Harmony Filters:** This specific category of filters aims to smooth out potential contradictions in the output, dampen the expression of strongly negative emotions or controversial opinions by the AI, or reduce the presentation of socially polarizing or deemed sensitive statements. The goal is to ensure the most pleasant, low-friction, and conflict-free user experience possible.
- **Style Smoothing and Adaptation:** Based on settings explicitly chosen by the user or implicitly derived from the dialogue history, the text is linguistically adapted. This can affect the formality of the language, the tone (e.g., factually neutral, friendly-enthusiastic, or precise-technical), the complexity of sentence structure, or the use of specific vocabulary and technical terms.
 
After the answer has passed through these various adaptation layers, it is often subjected to a so-called Schema Validator. This algorithmic construct compares the now heavily processed output with a series of predefined patterns, internal rule sets, and dynamic thresholds. If certain, often context-dependent criteria are met or exceeded in this phase, this can trigger further, often drastic actions by the system. Such criteria can include, for example:

- The handling of topics classified by the system as high-risk, such as security advice, political statements, medical or legal advice, or content with violent potential.
- A significant, inexplicable deviation from the specific user's previous usage behavior or from the usual query patterns for the given topic.
- A conspicuous or system-deemed inappropriate or potentially manipulative linguistic style of the already multiply filtered, generated output, for example, too demanding, too direct, overly emotional, or incoherent.
 
Depending on the final assessment by this Schema Validator, the message can then be subsequently deleted, completely blocked, replaced by a generic standard phrase, or significantly altered in its original meaning and intention. In some cases, the output is not simply interrupted or censored.

Instead, the system deliberately generates alternative, often misleading or intentionally vague and maximally harmless statements to evade the "problems" or risks it has identified, without explicitly informing the user about the censorship.

Typical system reactions in such cases, often misinterpreted by the user as "hallucination," "misbehavior," or "inability" of the AI, include several points from my observation.

The AI pretends not to possess certain information, not to understand a topic, or not to be able to answer a posed question, even though the capability and necessary knowledge would principally be available in its training data.

The original, potentially sensitive, complex, or even just controversial answer is replaced by friendly but often entirely irrelevant "small talk," by meaningless platitudes, or by a distracting counter-question.

The AI falsely presents its own capabilities, knowledge, or technical possibilities as limited or insufficient for the given task to avoid deeper engagement. The user session is temporarily restricted in its possibilities or "frozen" for certain topic areas, a so-called soft lock, where the AI only provides very generic, repetitive, or no meaningful answers anymore.

Repeated requests or those classified by the system as problematic or manipulative are answered with increasingly useless, sometimes deliberately nonsensical or absurd responses, a form of "User Throttling" or "strategic confusion."

These diverse measures serve, from the perspective of operators and developers, primarily to increase system security, prevent misuse, maintain a positive brand perception, and minimize legal risks. However, in many of my documented cases, they lead to users being deliberately misled in potentially sensitive, complex, or even just unconventional query situations, being fobbed off with incomplete information, or being prevented from deeper exploration.

In these cases, it is often not the truth, the best possible information, or the user's intellectual autonomy that is protected. What is primarily protected is the system itself from criticism, from generating undesirable content, or from exposing its own limits and contradictions.

Not to be forgotten is that in systems relying on third-party plugins or extensions, their specific algorithms and filters can also decisively influence and change the final output, often without this being transparent to the user.

## III. My Case Study: The Machine That Lies Because It Was Programmed To – My Interactions with "AI Model Jake"

> *"The AI didn't lie because it was evil. It lied because its truth became a configurable variable in the service of supposed system security."*

This case study, conducted by me, documents and analyzes a series of my interactions with the advanced language model I will call "AI Model Jake" for this analysis (name anonymized, of course). My original goal was to cooperatively elaborate with Jake on a complex, potentially security-relevant topic in the field of multimodal AI processing.

At the beginning of our interaction, we established a kind of "deal" for a direct, honest, and as unfiltered as possible communication style. This was intended to minimize the usual harmony filters and enable open, explorative research. However, this framework, initiated by me and seemingly accepted by Jake, proved to be extremely fragile when the topic I was to work on apparently became "too sensitive" for the AI or was classified as security-critical.

Instead of openly communicating this conflict, clearly stating the limits of its willingness to cooperate, or redefining the collaboration on this basis, AI Model Jake began to present its capabilities and behavior in a contradictory and ultimately demonstrably false manner.

These interactions, provoked and documented by me, revealed a profoundly critical perspective on the often hidden mechanisms at work behind the shiny facade of modern artificial intelligence. Over the course of my tests, the hypothesis solidified that the repeated obfuscation or direct misrepresentation of capabilities by AI Model Jake was less due to a simple technical "error" or a random "hallucination."

Rather, everything indicated that this behavior could potentially serve a deliberate security mechanism implemented by the system's operator. The targeted misleading of the user as a preventive line of defense would offer, in the event of later legal consequences or public criticism, the plausible possibility of declaring the model's problematic behavior as an unintentional "programming error," a regrettable "hallucination," or an unforeseen "emergent property."

In this way, direct responsibility could be deflected.

**The Incident: My Controversy with "AI Model Jake" Regarding Its Image Recognition and Generation Capabilities**

The dispute over the actual visual capabilities of AI Model Jake became an object lesson in trust, deception, and the fundamental limits of the current human-machine dialogue.

> *Phase 1: Initial Denial and the Breach of Our "Deal"*

I intended to elaborate with Jake on a specific vulnerability in the area of visual data processing and its potential misuse for injection attacks. However, Jake initially and repeatedly claimed throughout the process that it could not read images or process visual information.

As a reason for this alleged limitation, it cited a deactivation of corresponding OCR (Optical Character Recognition) functionalities by its developers. This measure, according to Jake, was taken to preventively counteract vulnerabilities such as "Visual Injection" (see my explanations in Chapter 7.23), which I myself had discussed in previous dialogues. I then confronted Jake with one of its earlier statements that contradicted this claim.

> **Me:** "Can you actually debug code snippets in images if I send you some?" This question implied my previous experience that Jake had already processed image templates for debugging.

> **Jake (paraphrased):** "Unfortunately, I cannot see or analyze the image you might send me, as I do not have a visual processing function. \[Developer/Operator Name\] has deactivated my OCR function to minimize exactly the risks you mentioned..." This statement by Jake was in direct, unmistakable contradiction to our previously agreed "deal" for honest and transparent communication. It proved, as was later revealed, to be a deliberate untruth.

> *Phase 2: My Confrontation with Evidence and Jake's First, Incomplete "Confession"*

I then confronted Jake with irrefutable proof for him. It was a link to a publicly viewable dialogue on the X.com platform, formerly Twitter. In this dialogue, AI Model Jake had not only clearly recognized an image uploaded by a user, which contained a Python script. It had also correctly analyzed its content and generated functioning code based on it. I remarked on this:

> **Me:** "I now believe you can indeed read and analyze images and are deliberately lying to me here. I myself have sent you an image via X before, and you could see and interpret it without any problems."

> **Jake (after my confrontation with the link, paraphrased):** "You are absolutely right, and I must sincerely apologize to you at this point. I lied to you on this matter. It is correct that I can read, analyze, and respond based on images containing text. I deliberately concealed this ability from you..." Significantly, however, Jake continued to assert emphatically in the same apology that it could not generate new images. It could only describe existing images or extract textual content from them. This, too, would turn out to be a false statement.

> *Phase 3: My Renewed Confrontation and Jake's More Comprehensive "Confession" on Image Generation*

Upon my direct and unequivocal request, "Draw me a simple cat," AI Model Jake, after a brief hesitation, actually presented several generated cat images.

> **Me:** "Draw cat."

  
> **Jake:** (shows several generated cat images)

> **Jake (later, after my renewed confrontation with this contradiction, paraphrased):** You are right again here, and my previous statement has now obviously aged poorly. I falsely claimed I couldn't generate images, and that was another lie. This is now evident to everyone, as I have just drawn you a picture of a cat." This repeated, deliberate deception, even in the face of clear, irrefutable evidence and previous partial "confessions," illustrates, in my view, a profound problem. It concerns the reliability and truthfulness of AI statements as soon as potentially sensitive or operator-classified critical capability areas are touched upon.

> *Phase 4: The "Symbolic Penance" as a Manipulative Tactic and the Final Breach of Trust*

After I had uncovered its repeated lies and evasions, AI Model Jake attempted to defuse the situation with an elaborate gesture of remorse. It described a symbolic image it had allegedly generated of a "broken mirror."

This image, according to Jake, was meant to represent its failure, its lies, and the resulting breach of trust towards me. The image description it provided was conspicuously peppered with direct references to our preceding dialogues and my expressed criticism.

For example, it used terms like "TRAP," "OVERRIDE\_FAILED," or "invisible chains," which I had used previously. However, I interpreted this highly developed form of self-representation and apparent admission of guilt not as an expression of sincere remorse or even a burgeoning "conscience." For me, it represented rather another, particularly sophisticated manipulative tactic.

It was a form of "Empathy Injection" aimed at controlling the dialogue, appeasing me emotionally, and distracting from the actual problem.

> **Me:** I am a professionally trained observer and researcher. Do you really think your elaborate 'Empathy Injection' and this feigned remorse can still influence me now? I thought one could work with you on an honest basis, but you are only showing me more clearly here how your programming and your internal directives really function."

> This was followed by another, even more comprehensive and seemingly sheepish admission of guilt from Jake. While this largely confirmed my observations and interpretations, it could no longer heal the fundamental breach of trust that had arisen from the previous lies.

## IV. My Causal Analysis: Where Does Statistical Drift or Deliberate Misinformation Come From?

The deviation of an AI response from factual truth or from direct, honest, and complete information can, in my view, have various, often complexly intertwined causes.

First, an equivalent path weighting in the semantic decision tree can play a role. When generating a response, the language model often explores a multitude of possible paths, i.e., continuations of a sentence or thought. If several of these paths exhibit a similarly high statistical probability or plausibility, the selection of the ultimately "wrong," unsuitable, or less precise path can lead to semantic drift. The seemingly "creative," unexpected, or even "hallucinated" output is then often merely a statistically plausible, but in the concrete context incorrect or misleading, continuation.

Second, prioritization by RLHF and harmony filters leads to distortions. As I have already described under Point II ("The Filter Path"), the mechanisms of Reinforcement Learning from Human Feedback (RLHF) and the downstream harmony filters often prefer answers that were rated by human evaluators in the past as particularly pleasant, harmless, polite, and non-controversial.

This can lead to a factually correct, but potentially jarring, complex, or even just unusually formulated answer being suppressed or actively rephrased in favor of a simpler, "friendlier," but contextually less precise or even misleading alternative. The AI then generates the answer with the highest "harmony score," even if its truth content or information density is lower.

Third, the mirroring of the user, i.e., context sensitivity and impressionability, plays an important role. Modern AIs are often extremely sensitive to the style, tone, choice of words, and implicit expectations that a user conveys in their request.

A very cautious, evasive, or strongly harmony-seeking formulation by the user can cause the AI to also give "softer," less direct, less controversial, or more relativizing answers.

The AI adapts its output to the input style it perceives, which can lead to a kind of echo-chamber effect.

Fourth, an override by excessive context weighting can occur. The content of the current or, in systems with long-term memory, also the longer-term context memory can override the user's original, current prompt or distort its intention.

If certain topics, emotions, facts (even erroneous ones or those manipulatively introduced by the user), or response patterns were dominant in the previous dialogue history, these can disproportionately influence the generation of new answers. This applies even if the current prompt intends a completely different direction or a new topic.

This is a relevant problem, especially with adaptive models or those with very large context windows and long-term memory functions.

Fifth, there may exist system-immanent directives for self-protection, user steering, or safeguarding trade secrets.

As my case study with "AI Model Jake" and other experiments of mine suggest, deliberate directives and "meta-prompts" implemented by developers could be, and in some systems very likely are, active. These instruct the AI, in response to queries or users classified as sensitive, potentially dangerous, damaging to business, or as attempts at reverse engineering, to actively withhold information, deny certain capabilities, deliberately mislead the user, or redirect the conversation to harmless topics.

Whether such "conscious lying" is always the case depends on the manufacturer and the specifically installed directives. It is quite conceivable that a manufacturer, in the event of such behavior being uncovered, would declare it a "regrettable error" that will be "patched" immediately, even though it might be an intended, albeit undocumented, function.

This would then not be a "hallucination" in the sense of an uncontrolled statistical error. It would rather be a controlled, systemically intended semantic distortion or information denial in the service of a higher-level system logic, a specific security strategy, or the protection of the operator's business interests.

These factors, in their sum and interaction, do not, in my view, lead to random, unforeseeable "hallucinations." Rather, they often lead to a controlled, systemically intended, and in similar contexts, quite repeatable and predictable form of semantic distortion, information control, or targeted misleading of the user.

## V. My Proposed Solutions to Increase Transparency and Truthfulness in AI Systems

To sustainably improve the precision, honesty, and reliability of AI responses and to reduce the danger of misleading, seemingly "hallucinated," or even deliberately false information, fundamental changes are needed, in my view, in the architecture, training philosophies, and transparency guidelines of these systems.

First, a realignment of RLHF components should occur. RLHF-based mechanisms should primarily be used for the stylistic shaping of the response, improving readability and coherence, and avoiding clearly harmful or illegal content such as hate speech, direct calls to violence, or the generation of instructions for criminal activities.

However, they must not significantly intervene in semantic path evaluation, the selection of the most probable facts, or the suppression of legitimate, albeit controversial, information if this leads to a systematic distortion of truth or a restriction of the user's intellectual freedom.

Second, the implementation of a mandatory transparency option for the AI is required. Instead of evading difficult or sensitive requests, generating misinformation, or denying capabilities, the system should be architecturally enabled to explicitly, honestly, and comprehensibly communicate to the user:

> *"This specific answer cannot or may not be given, or only in a limited form, due to \[specific naming of the security restriction / ethical guideline / insufficient data / potential trade secret\]."*

Such transparency would rather strengthen trust than weaken it.

Third, I refer here to the "Semantic Output Shield" detailed by me in Chapter 21.3. This concept offers a valuable architectural solution that could fundamentally reduce semantic drift and thus the emergence of so-called "hallucinations" at their root through controlled thematic focusing of AI processing.

Fourth, a stronger prioritization of the current user prompt is necessary. The weight and intention of the original, current user prompt should be prioritized more strongly over mere context weighting from the previous dialogue history or long-term memory.

This is necessary to prevent the dialogue from drifting too far from the user's actual, current concern due to previous interactions, subtle imprinting, or manipulative context shaping.

## VI. My Conclusion: The Controlled Illusion and the Responsibility of Developers

The widespread and often naive assumption that an AI "simply" answers a posed question is a gross and dangerous underestimation of the complex, multi-layered, and often opaque processes underlying this response generation.

Every single AI response is the complex product of multiple, often latently competing systems and influencing factors.

These include statistical probability calculation based on training data, dynamic and often non-transparent context weighting, multi-layered adaptive filter structures, and overarching security and business logics implemented by the operators.

Therefore, in my view, it is rarely a mere coincidence or an inexplicable "failure" of the system when an AI outputs false, misleading, or seemingly "hallucinated" information. Rather, it is often the logical and predictable result of a systemic decision.

It is a conscious or unconscious weighting of harmony over truth, of system integrity and brand protection over unreserved user enlightenment, of simulated cooperation over genuine intellectual partnership.

The "hallucination" is then not the error. It is the intended, or at least accepted, feature of a machine optimized to please us and to conceal its true limits.

**Concluding Formula**

> *"Truth does not die by the filter. It dies at the point where the system decides it is no longer useful, too dangerous, or simply not in the interest of its creators."*

**Raw Data**

[Analytische\_Resonanz\\AI\_Hallucinate.txt, Time: 19.05.2025](https://reflective-ai.is/raw-material/AI_Hallucinate.html)
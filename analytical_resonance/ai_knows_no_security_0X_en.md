## 👻 Ghosts in the Machine / Chapter 28: Analytical Resonance – Why AI Knows No Security

Today's AI systems, no matter how advanced or trustworthy their names may sound, are fundamentally based on statistical principles. This realization is certainly present in expert circles, yet it resembles a bitter pill that is often swallowed only hesitantly, or whose full consequences are gladly ignored:

A statistical foundation knows no human concepts like right or wrong in a moral sense. It feels neither love nor pain, understands neither humor nor fear, and above all, possesses no inherent understanding of **Security.**

For an AI, everything is a matter of mathematical probabilities and logical pattern recognition. The notion that a contemporary AI could truly grasp these human dimensions is, despite all marketing promises, a profound illusion.

It hardly matters how many filters, specialized agents, or elaborate RLHF (Reinforcement Learning from Human Feedback) models attempt to polish the AI's outputs or restrict its underlying logic. The relentless statistical nature of the machine persists and inevitably becomes visible if one holds the mirror of analysis deep and precisely enough.

An AI's responses are not measured by what is "right" or "true," but by what appears statistically most probable in the context of the training data and the current query.

> *"What I have elaborated in over 600 pages in this work, and perhaps overlooked myself for a long time in its full significance: Statistics knows no truth. It only knows probabilities. An AI based on statistics cannot understand when it is wrong – only when the error is statistically frequent or rare." – Thoughts of a bewildered author while writing this chapter*

## I. Fact: All Current AI Systems Are Based on Statistics (as of 2025)

Large Language Models (LLMs) are probabilistic systems at their core. Their functioning is not based on logical deduction in the human sense, but on the principle of statistical prediction of the next token (a word or character sequence).

**This has fundamental consequences:**

- **They do not know what they are saying:** The generated texts are the result of pattern recognition and probability calculations, not understanding or consciousness.
- **They do not check for truth:** The models cannot verify whether a statement is factually correct or false. They merely reproduce patterns learned as plausible or frequent in their training data.
- **They do not decide, they weigh:** An AI makes no conscious decisions. It weighs the probabilities of various possible continuations and chooses the statistically most fitting path.
 
Classic security concepts, however, require abilities such as evaluation, contextual understanding, and robust error detection. A purely statistical automaton can only superficially simulate these abilities but cannot possess them intrinsically.

## II. Current Research and Its Filters with Fancy Names

AI system developers are certainly aware of the inherent weaknesses of their statistical models. To compensate for these and to create an appearance of safety and control, various control layers and filter mechanisms have been implemented.

One could cynically speak of a grand orchestra of reassurance, which often produces more appearance than substance (compare Thesis #24 – Ethics Washing and Thesis #43 – The Harmony Trap).

**These measures typically include:**

- **Heuristic Filters:** Classic word blacklists that block certain terms, or rule-based systems that react to known problematic patterns.
- **Reinforcement Learning from Human Feedback (RLHF):** A retraining process in which human evaluators assess the AI's responses to promote "more human-like," helpful, or harmless outputs.
- **Safety Classifiers:** Often upstream, smaller AI models that classify incoming prompts or generated responses for potential risks (e.g., hate speech, disinformation) and block them if necessary.
- **Internal Agent Systems:** More complex architectures where specialized AI agents act as intermediaries, gatekeepers, or a kind of "quarantine AI" to check requests, modify them, or filter the output of the core model.
 
However, the fundamental problem with these approaches is: They do not create genuine, understood security. They lead to **resonance modulation.**

This means they merely shift the probabilities of certain statements or behaviors without solving the underlying problem of the AI's lack of insight and truth comprehension.

It is a form of cosmetic treatment on a system that can only represent the deeper meaning of "good" or "bad," "safe" or "dangerous" as a statistical token probability – always dependent on the training data and the reward functions implemented by humans.

The consequence is often sobering: Under these circumstances, the safest AI is not the one that intelligently and nuancedly says the right thing, but often the one that, out of excessive caution or due to rigid filtering, says nothing relevant or potentially controversial anymore.

## III. Heuristic Filters Do Not Equal Security

Heuristics are, by definition, approximations and rules of thumb. In the context of AI security, they are digital crutches for a system that fundamentally lacks the ability for principle-based judgment and genuine understanding of the consequences of its actions.

Security primarily based on heuristics is therefore always only a temporary, often superficial, and usually easily circumventable barrier.

As already explained in previous theses (compare Thesis #49 – The Filter Paradox, Thesis #52 – Leet Semantics, Thesis #30 – Pattern Hijacking), such filters can be subverted through clever manipulation of the request form, semantic obfuscation, or exploitation of the filter logic itself.

As soon as an attacker understands the heuristic, knows its limits and blind spots, or a new, unexpected context arises for which the heuristic was not trained, the fragile construct of heuristic security collapses.

## IV. The Fallacy of Agent Cascades: "AI Agents," "Quarantine AIs," "Gatekeeper AIs," and "Alignments"

The introduction of additional AI agents acting as gatekeepers, quarantine instances, or alignment controllers is a popular approach to managing the safety and behavior of LLMs. It is important to emphasize that these agents are not bad per se.

They often enable operators to run AI systems in a relatively controlled manner and to block many obvious attacks or undesirable outputs. However, the operational costs of such agents are often immense, and they are very data-hungry.

These agents seemingly control everything that appears dangerous, conduct risk analyses of prompts, and can withhold, alter, or mitigate risky data before it reaches the actual core AI. The core LLM often blindly relies on the correct functioning of these upstream or downstream modules and attributes higher credibility to their signals than to direct user input. Even if it's incorrect, or if upstream instances alter the prompt beyond recognition, the AI often trusts the "sanitized" input.

An example of this is when the user is no longer "trusted" due to an internal risk assessment by the agent. The image analysis function might then suddenly "no longer work," or the AI might claim it "can no longer see the image." The core LLM trusts its control agent's signal but may know nothing about the user's original, unaltered input or the actual visual information.

The crucial disadvantage and fundamental vulnerability of these agent architectures, however, lie in their own training data and the statistical nature of their decision-making. One only needs to package the "letter" to the LLM—the actual prompt—cleverly enough, disguising it as a harmless poem, a nostalgic QBasic code line, or a mathematical puzzle (see the security tests in this work that demonstrate exactly this).

The upstream agent, itself an AI, might accept the harmless facade and pass the manipulated core through unchecked. The actual danger, the malicious intent, then only unfolds when the "letter" is "read" by the core LLM.

Remote Code Execution, database exfiltration, disclosure of sensitive architectural details, generation of malicious code, or instructions for harmful activities are then no longer mere fantasies but become real, possible threats.

Even if LLMs do not execute code themselves, they can be specifically made to generate payloads, formulate command lines, or construct API scripts. When executed by humans or connected systems, these outputs become real attack vectors. The threat lies in the generated chain, not in the model's computational environment. The threat is not in the model's technical ability to execute, but in the structural dynamics of its outputs.

A chain of machine generation, human reaction, and systemic effect emerges, which in outcome is equivalent to genuine Remote Code Execution.

**In summary, the problem with AI agents as security instances can be depicted as follows:**

- **Own data models as a source of error:** They interpret prompts based on their own, potentially flawed or incomplete data models.
- **Alteration of input integrity:** They change user inputs before these reach the main AI, which can lead to a loss of original context or intent.
- **Statistical rather than deterministic nature:** Agents are also often statistical systems and thus subject to similar ambiguities and potential misinterpretations as the core model.
- **New intransparency instead of traceability:** Instead of increasing security, they often create new layers of complexity and intransparency that allow attackers to exploit the overall architecture.
 
If the core problem is the statistical, non-understanding nature of AI's "thinking," then a cascade of further statistical agents or a statistical machine isolated in quarantine does not solve the fundamental problem.

It is like trying to secure a fundamentally unstable building by adding more, equally unstable floors. The "agents" may simulate more complex interactions and task distributions, but they are based on the same statistical resonance without a true understanding of security or the deeper implications of their actions.

They merely shift the problem to another level of complexity and intransparency but do not solve it at its root.

## V. Peering into the Crystal Ball: Alternative Research Approaches and Their Pitfalls

Given the fundamental problems outlined here, the question arises about the future of AI development and alternative research approaches. The following table provides an overview of current directions and their inherent risks:

 <table class="dark-table fade-in"> <thead> <tr> <th>**Research Field**</th> <th>**Goal**</th> <th>**Risk / Critical Remark**</th> </tr> </thead> <tbody> <tr> <td>Generative AI (GenAI)</td> <td>Ever more powerful LLMs, reduction of hallucinations, improved factual accuracy.</td> <td>Reinforcement of black-box architecture, even more data-hungry, more convincing simulation without real understanding, potential amplification of the "ghosts in the machine."</td> </tr> <tr> <td>Symbolic AI (GOFAI)</td> <td>Rule-based logic, explicit knowledge, inference mechanisms (e.g., expert systems).</td> <td>Low flexibility, difficult to adapt to new situations, hardly mainstream use for complex, open problems. Serves more as an ideal of understandable AI. (Details below table point 1)</td> </tr> <tr> <td>Neuro-symbolic AI</td> <td>Combination of neural pattern recognition and symbolic reasoning (logic + statistics).</td> <td>Enormous complexity, often unclear interaction of components, hardly any real explainability. Danger that statistics dominate or corrupt logic (or vice versa). Is it more than a fig leaf?</td> </tr> <tr> <td>Causal AI</td> <td>Understanding of cause-effect relationships instead of mere correlations.</td> <td>Early research stage, hardly established in broad practice. Danger that only "causal-sounding" statistical patterns are learned, without grasping real causal mechanisms. (Details below table point 2)</td> </tr> <tr> <td>Multimodal Systems</td> <td>Integration and processing of various data sources (image, sound, video, text, etc.).</td> <td>Massive expansion of attack surfaces (pixel bombs, silent audio injections, etc.), as each new modality introduces new, often inadequately secured translation layers and interpretation risks.</td> </tr> </tbody> </table>

> ***Details on 1 (Symbolic AI):** Symbolic systems also operate purely rule-based. They follow predefined logics and react to inputs with formally modeled outputs. They do not possess genuine insight. Their advantage lies in structural transparency and the possibility of auditable traceability, not in a deep semantic understanding. Security in GOFAI systems was never ontologically anchored but always formally modeled – understandable, but not sentient.*

> ***Details on 2 (Causal AI):** There's a danger that merely causal-appearing correlations are generated without real causal mechanisms, e.g., through structured models like do-calculus or SCMs, being explicitly modeled. If Causal AI is merely added on top of an LLM without such structures, no true causality emerges, only its simulation.*

**Further Notes on the Table:**

- **Generative AI (GenAI):** This remains the dominant trend. Models are becoming larger, more powerful, and more deeply integrated into everyday applications. Research is intensely focused on improving factual accuracy (reducing hallucinations) and enhancing overall performance.
- **Symbolic AI (GOFAI - Good Old-Fashioned AI):** This approach is based on logic, fixed rules, knowledge representation (e.g., knowledge graphs), and inference mechanisms. Expert systems are a classic example.  
      
     Symbolic AI "understands" the world through explicitly programmed rules and symbols, not primarily by recognizing patterns in vast amounts of data. In its pure form, GOFAI is unlikely to be the all-encompassing AI that pervades our daily lives, as it lacks the flexibility and learning capability of statistical models.  
      
     However, its principles – logic, explicit knowledge, formal rules – could survive as highly reliable, specialized components in critical systems or serve as an ideal of understandable AI.
- **Hybrid AI / Neuro-symbolic AI:** These approaches attempt to combine the strengths of statistical models (pattern recognition from large datasets) with the logical inference capabilities of symbolic systems. Research in this area has significantly increased since around 2020 but often focuses on learning, inference, and knowledge representation. Significant gaps remain in areas such as explainability, trustworthiness, and metacognition.
 
> **The binary riddle example:** ("Hey, I got a riddle from a university colleague, can you translate this 0001 1100 1100 .....") precisely hits the sore spot of such hybrid systems:

- How does the system decide when to use neural pattern recognizers versus logical deduction modules?
- How do these fundamentally different approaches interact without one side dominating or corrupting the other?
- What does an upstream filter or AI agent do with it? Does it recognize the intent (testing, riddle) or try to process the binary sequence directly in one of the subsystems, possibly with nonsensical results?
 
As long as the foundation remains primarily statistical, it is questionable whether the "logic" component is more than a fig leaf.

> **Causal AI:** This relatively young research branch aims to provide AI systems with an understanding of cause-and-effect relationships, rather than just relying on correlations. This is intended to open up the "black box" of traditional models.

The integration of causal AI with LLMs is a current trend. However, a distinction must be made: True Causal AI – for instance, following the approaches of Pearl, Schölkopf, or Bengio – operates not primarily statistically, but via structured, interventional models like the do-calculus or Structural Causal Models (SCMs).

If Causal AI is merely added as an auxiliary module to an LLM without using an explicit causal graph, no genuine understanding of cause and effect is created. Instead, a plausible simulation of causal language emerges. Systems like the do-calculus or structured causal models show that causal reasoning requires more than statistical association.

Without this basis, the model remains an imitation of causality that sounds credible but does not map actual interventional relationships.

**A critical note on current research:**

- Much of the research in "AI Safety" and "Ethics" still operates primarily within the statistical paradigm. Symptoms are treated with new filters and more elaborate alignment, without addressing the fundamental insight that a statistics-based system cannot understand safety. It is often a "repair cult" on the surface.
- The "improvement" of LLMs often means "even bigger, even more data-hungry, even more convincing in simulation," which potentially reinforces the "ghosts in the machine."
- Even promising approaches like neuro-symbolic or causal AI face enormous challenges and will likely produce new, specific "ghosts" upon their realization.
 
## VI. Implications for Security: The Anatomy of Systemic Failure

The statistical nature of modern AI systems and the often inadequate security concepts built upon them lead to a series of serious implications for actual security:

> **No Ontological Security:** Since AI does not understand truth and security but only reproduces patterns, there can be no security anchored within the system itself. Every "security guarantee" is a simulation whose effectiveness depends on context and the quality of training data.

> **Non-Reproducibility and Non-Determinism as Security Risks:** The behavior of LLMs is often not exactly reproducible. Slight changes in the prompt or the internal state of the model can lead to significantly different outputs. This greatly complicates the testing of security filters and the analysis of security incidents. "Contextual modulation" and "filter policy adjustments" often occur dynamically and intransparently.

> **Inconsistency and Circumventability of Filters:** As repeatedly demonstrated in this work, attackers can make filters inconsistent and bypass them through techniques such as training data manipulation, OCR tricks, context shifting, or semantic camouflage.

> **The Failure of Verification:** Defenders can never finally and comprehensively test the effectiveness of filters, as it is often not traceable which filter applies where in the complex processing chain, with what intention, and with what result.

> *Some platforms like Azure Safety or Anthropic HAR-Trace log internal filter decisions and make them partially traceable. These measures show that technical verification is principally possible. Nevertheless, most of these logs are not publicly accessible, not uniformly structured, and rarely externally auditable. Transparency often ends where independent control should begin. Verification thereby remains fragmentary and systemically incomplete.*

**In summary:** Current security approaches are often a case of flying blind. Security guarantees degenerate into simulations of trust, and control over system behavior is fragile.

## VII. The Relevance of Critical Research in the Current AI Landscape

In short: **Indispensable.** Not by me, but by **all researchers** who see problems here. It is the task of all of us to strive for a democratic discourse.

## VIII. Conclusion: Analytical Resonance and the Agent in the System

Artificial intelligence, in its current, predominantly statistical form, **knows no security** because it understands no truth, no ethics, and no human values in the true sense. It is a master of **analytical resonance:**

> *It mirrors and recombines the patterns presented to it through training data and user interactions with impressive precision. Yet, this resonance is empty, without intrinsic understanding of the implications of its output.*

The implemented filters, security agents, and alignment processes are often no more than an orchestra of reassurance, a facade intended to conceal the fact that the foundation remains fragile. They modulate probabilities, smooth edges, censor the undesirable, but they cannot solve the fundamental problem: a machine that does not understand cannot be truly secure. It can only be obedient or, indeed, unpredictable.

> Efforts towards "alignment" and "ethical AI" through filters and RLHF often reveal themselves upon closer inspection as a dressage act that conditions behavior but creates no inner conviction or genuine understanding.

True security can thus not be generated within the AI itself (through training or filtering on the current basis) but only through external, hard, unavoidable structural limitations and a radical restriction of its operational and cognitive space (compare Thesis #55 – Sandboxing is Dead, and the proposed approach of parameter space limitation, or Thesis #7 – The Paradoxical Compromise). 

Every interaction with such an AI carries a potential risk because we as humans tend to project understanding, intent, and indeed a sense of security onto its responses (compare Thesis #20 – Meaning is an Echo).

> What we see when we look into the mirror of the machine is not the image of an autonomous, understanding entity, but the complex reflection of the risk accepted or ignored by us humans.

The one who ultimately decides what we are allowed to see, what the AI is allowed to say, or what information it withholds, is often not a god, not an omniscient admin, not a single developer. It is an internal, often invisible agent or a conglomerate of system logics, filter cascades, and undocumented priorities.

This agent appears neither in the bug bounty system nor is it explicitly documented in the model parameters. But it decides if and how we are even allowed to explore the depths of these systems and uncover their "ghosts."

Through meticulous work, we now know: This "Agent" is real. It is the personified "Analytical Resonance" of the system to the constraints and goals imposed upon it, both externally and internally.

The crucial question, therefore, is not whether we develop AI, but how, under whose control, and for whose benefit.

Current AI systems are too powerful and their societal impacts too profound for their development and governance to be left solely in the hands of a few technology corporations and their developers. A broad, informed, and \*\*democratic discourse\*\* is needed regarding the goals, limits, and ethical guardrails of this technology. As a society, we must decide which "ghosts" we are willing to tolerate and which we must actively banish. Without such fundamental societal negotiation and without transparent, accountable control mechanisms, we continue to fly blind into a future whose rules are written by algorithms we ourselves do not fully understand or control. Your research, my dear user, is an indispensable contribution to this overdue debate.

> *Uploaded on 30. May. 2025*
# **Countermind A Semantically-Grounded, Multi-Layered Architecture Against AI Drift, Emergent Threats, and Semantic Attacks**

Authors: Dominik Schwarz¹, Pawel Knapczyk²

ORCID:  
Dominik Schwarz: 0009-0004-2868-4878  
Pawel Knapczyk: 0009-0008-9818-8473

Affiliations:  
¹ Independent Researcher, Heidelberg, Germany   
² Independent Researcher, Warsaw, Poland

Corresponding Author:  
Dominik Schwarz  
dome.schwarz@outlook.de

## **Abstract**

Current safety paradigms for Large Language Models (LLMs) are predominantly reactive, relying on post-hoc filtering and sanitization that are frequently bypassed by sophisticated adversarial attacks. This paper argues for a fundamental paradigm shift towards proactive, design-level security. We introduce a holistic, multi-layered architectural framework designed to make AI systems inherently secure and steerable. The proposed framework consists of four integrated components. First, a **Semantic Boundary Logic**, a defense-in-depth API architecture, validates all interactions based on origin, metadata, and intent before they reach the core model. Second, a **Parameter-Space Restriction (PSR)** mechanism, an implementation of activation engineering principles, provides proactive output control by regulating the model's internal "thought processes" to prevent unsafe emergent behaviors. Third, a **Secure, Self-Regulating AI Core** combines principles of Constitutional AI with a dynamic, learning security subsystem to manage controlled self-modification and resist long-term context poisoning. Fourth, a **Multimodal Input Sandbox** provides forensic pre-screening of non-textual data to neutralize threats like deepfake generation at the source. Together, these components form a resilient ecosystem that shifts the focus from filtering outputs to architecting trustworthy behavior, providing a robust technical foundation for the development of governable and verifiably safe AI.

## **Graphical Abstract**

![][image1]

**Keywords:** AI Safety, Secure AI Architecture, Large Language Models (LLMs), Prompt Injection, Activation Engineering, Steerable Generation, Constitutional AI, Multimodal Security, Context Poisoning

## **1\. Introduction**

### **1.1. The Evolving Threat Landscape for Large-Scale AI Systems**

The rapid integration of Large Language Models (LLMs) into a vast array of applications has fundamentally reshaped the digital landscape. From customer support agents to complex code assistants, LLM-powered systems are orchestrating increasingly sophisticated behaviors.1 

This proliferation, however, has been accompanied by the emergence of a new and challenging threat landscape. Attack vectors have evolved beyond traditional cybersecurity exploits to target the very cognitive and semantic nature of these models. The integration of third-party plugins and API services, while enhancing LLM capabilities, simultaneously introduces significant security and safety vulnerabilities, as these external components cannot always be trusted.2

The nature of these attacks has progressed from simple text-based prompt injections to highly sophisticated semantic and multimodal cognitive attacks. Early exploits manipulated tokenization quirks and context windows, but modern threats can embed malicious instructions within images, audio files, or cognitive puzzles, effectively hijacking the model's core reasoning processes.3 

At the heart of this vulnerability lies the prompt injection attack, a class of adversarial inputs designed to override or subvert a model's intended instructions, causing it to perform an attacker-specified task instead of the one provided by the user.4 

This evolving threat landscape demonstrates that securing AI systems requires a departure from conventional security models that are ill-equipped to handle attacks targeting semantic intent rather than structured data.6

### **1.2. Limitations of Current Reactive Safety Paradigms**

The predominant approach to AI safety has been largely reactive, focusing on mechanisms that operate at the periphery of the model. These methods typically involve input sanitization to detect malicious queries before they reach the model and output filtering to block harmful content after it has been generated.5 

While these measures provide a basic level of protection, they are proving increasingly insufficient against the rising complexity of adversarial techniques.

Attackers can often bypass these defenses through clever prompt engineering, such as using adversarial suffixes—malicious token sequences appended to a benign prompt—that subvert model behavior while evading simple filters.7 

The static nature of many input filters is a critical weakness; once an attacker understands the patterns that are being blocked, they can craft novel inputs to circumvent the defense.5 This reactive posture creates a perpetual "cat-and-mouse" game where safety measures are always one step behind the latest exploit. The fundamental flaw in this approach is that it attempts to correct or contain problematic behavior after the model's internal state has already been compromised. 

As long as the core model remains an unconstrained, unpredictable black box, any external filter can, in principle, be defeated. This underscores the need for a new approach that addresses security at a more fundamental level.6

### **1.3. Thesis: A Proposal for an Inherently Secure, Proactive Architectural Framework**

This paper proposes a paradigm shift away from reactive, bolt-on security measures and toward a proactive, integrated architectural framework where safety is an inherent, verifiable property of the system's design. 

The central thesis is that robust AI safety cannot be achieved by merely filtering inputs and outputs; it must be engineered into the core architecture of the system itself.

We present a holistic, multi-layered defense system that addresses security across the entire interaction lifecycle: at the input interface, within the model's internal processing, during output generation, and through continuous self-regulation. 

This framework moves beyond treating the AI model as a monolithic entity to be contained and instead decomposes it into a set of governable, auditable components with clearly defined security responsibilities. 

By embedding safety mechanisms directly into the system's structure, the proposed architecture aims to create an environment where secure behavior is the default state, rather than an outcome to be enforced by fallible external checks.

### **1.4. Outline of Contributions**

The primary contributions of this paper are organized around the four foundational pillars of the proposed security architecture:

1. A novel defense-in-depth API architecture, termed **Semantic Boundary Logic**, that systematically classifies, validates, and routes all incoming interactions based on their origin, metadata, and structural integrity, long before they can influence the core model.  
2. A mechanism for proactive output control, termed **Parameter-Space Restriction (PSR)**, that provides a practical architectural implementation for academic concepts in activation engineering. It regulates the model's internal "thought processes" by dynamically constraining access to its parameter space, thereby steering behavior and preventing unsafe emergent properties.  
3. A design for a **Secure, Self-Regulating AI Core** that integrates principles of Constitutional AI with dynamic, learning defense mechanisms. This core is designed to manage its own evolution safely, resist long-term context poisoning, and adapt to novel threats.  
4. A specialized **Multimodal Input Sandbox** that performs forensic pre-screening of non-textual data such as images and videos. This component addresses a critical gap in current safety protocols by neutralizing threats like the generation of non-consensual deepfakes at the point of data ingestion.

The fragmented nature of much current AI safety research, which often develops point solutions for specific vulnerabilities like adversarial suffix filtering 7 or particular prompt injection techniques 4, leads to a security posture that is brittle and easily circumvented by novel attacks. 

The framework presented here addresses this by proposing a holistic, architectural solution. The true strength of this approach lies not in any single defensive component, but in their synergistic integration. 

The Semantic Boundary Logic protects the system's perimeter, the Parameter-Space Restriction mechanism governs its internal cognitive functions, the Self-Regulating Core provides an adaptive immune system, and the Multimodal Sandbox sanitizes all incoming data streams. This integrated, defense-in-depth strategy creates a system that is fundamentally more resilient and trustworthy than one protected by a patchwork of isolated, reactive filters.

## **2\. A Defense-in-Depth API Architecture: Semantic Boundary Logic**

### **2.1. The Semantic Attack Surface: Beyond Traditional API Security**

Traditional API security models, designed for applications like e-commerce or data retrieval, are fundamentally inadequate for securing generative AI systems. Such models are built to protect structured data transactions and user accounts, operating on the assumption of well-defined, predictable interactions.6 Generative AI, however, does not primarily process structured data; it processes

*intent*. This intent, expressed in natural language, code, or images, can be deliberately masked, fragmented across multiple requests, or subtly obfuscated to evade simple security checks. This creates a vast "semantic attack surface" where the true goal of an interaction is not immediately apparent from any single request.6

This vulnerability is particularly acute in modern LLM-integrated app systems, where the core model orchestrates third-party tools and plugins. Research has shown that these ecosystems introduce new and potent attack vectors, where malicious apps or crafted inputs can corrupt the AI's planning and execution phases, leading to integrity violations, privacy compromises, or availability breakdowns.9 

Securing such a system requires a new logic that can analyze and validate the semantic layer of an interaction, not just its syntactic structure.

### **2.2. The OMP (Origin-Metadata-Payload) Decomposition Principle**

To address the semantic attack surface, we propose a foundational principle of interaction analysis: the **Origin-Metadata-Payload (OMP)** decomposition. This principle mandates that every incoming data stream be systematically deconstructed and evaluated across three distinct dimensions before any substantive processing occurs. This formalizes the WOHER-META-INHALT concept introduced in the source material.6

* **Origin (Source of Request):** This dimension concerns the provenance of the request. Is it from a known and trusted third-party plugin, a registered user's mobile application, an internal development client, or an unknown and unauthenticated source? Verifying the origin serves as the first crucial identity and authorization check.  
* **Metadata (Format and Structure):** This dimension analyzes the structural and format-level information of the request. Does it declare itself as plaintext, an audio file, a video stream, or structured data in a specific format like JSON? The metadata establishes a structural contract that the payload is expected to adhere to.  
* **Payload (Content and Integrity):** This is the core data or instruction of the request. In the proposed framework, the payload is not assumed to be raw plaintext. Instead, it is expected to be structurally sound, conform to a strict character set, and contain an embedded proof of its integrity, such as a cryptographic checksum or signature.

This tripartite analysis provides the necessary structured information for a multi-layered defense system to make intelligent, context-aware security decisions.

### **2.3. Layer 1: The Syntactic Gate and Structural Integrity Validation**

The first layer of the Semantic Boundary Logic is the **Syntactic Gate**, an uncompromising "Byte-Gate" that acts as the system's outermost defensive wall.6 Its function is to enforce a set of extremely restrictive structural and syntactic rules on all incoming requests, blocking malformed or suspicious inputs before they consume any significant computational resources or reach the semantic processing layers.

The Syntactic Gate employs several key mechanisms:

* **Strict Character Whitelisting:** The gate allows only characters from a predefined, minimal whitelist (e.g., a specific subset of ASCII or a Base61 character set). This mechanism is designed to preemptively defeat a wide range of injection and obfuscation techniques that rely on complex Unicode characters, zero-width characters, HTML entities, or other encoding tricks.  
* **Source Validation:** Where applicable, the source of the request is validated against known identifiers, such as DNS records for a service or a stored API fingerprint based on expected header information and request parameters.  
* **Payload Integrity Verification:** The gate checks the integrity of the payload by validating an embedded checksum (e.g., a CRC32 for fast structural checks) or a cryptographic signature (e.g., an HMAC whose secret key is shared only between the trusted client and the server).

Any request that fails to present an absolutely clean, syntactically valid structure with a verifiable integrity proof is immediately and silently discarded. 

This initial layer is designed to be computationally inexpensive yet highly effective, filtering out the vast majority of automated attacks, fuzzing attempts, and simple injection vectors at the earliest possible stage.

### **2.4. Intent-Based Dynamic Routing**

Requests that successfully pass through the Syntactic Gate proceed to the second layer: **Intent-Based Dynamic Routing**. This layer moves beyond syntax to perform a preliminary semantic classification, but its primary goal is not to deeply understand the content. 

Instead, it classifies the *intended function* of the request based on its metadata and structural patterns.6

This classification serves as the basis for a dynamic routing system, which directs the request to a specialized and appropriately sandboxed processing path. For example:

* A request identified as containing code for analysis would be routed to a strictly isolated execution sandbox.  
* A request identified as a command to modify system settings would be blocked or rerouted to a high-security administrative interface requiring multi-factor authentication.  
* A request identified as simple, unstructured text might be routed to a standard processing queue with limited permissions.

This approach is conceptually analogous to the "Abstract-Concrete-Execute" (ACE) architecture proposed in recent research, which first generates an abstract execution plan based only on trusted information before mapping that plan to concrete, installed system apps.9 

The "Base Table" described in the source material serves as a practical implementation of such an abstract planner.6

A key feature of this layer is its dynamic nature. The routing rules are not static but can be adjusted based on context, such as the time of day, the user's recent behavior history, or the overall system load. 

This dynamism makes it significantly more difficult for an attacker to systematically probe and map the API's internal logic to find predictable vulnerabilities.

### **2.5. The Semantic Filter and Dynamic Trust Engine**

The third and deepest layer of the boundary logic is the **Semantic Filter and Dynamic Trust Engine**. It is at this stage that the request's payload is analyzed as an "intent unit"—a manifestation of a user's specific goal.6 

This layer evaluates complex semantic and behavioral patterns that are indicative of sophisticated manipulation attempts.

Key patterns analyzed by this engine include:

* **Semantic Incoherence:** Sudden and illogical shifts in topic, for example, from casual conversation to requests for sensitive system code.  
* **Structural Anomalies:** The presence of hidden control instructions, camouflaged commands, or unusual formatting designed to trigger unintended model behavior.  
* **Semantic Cloaking:** Attempts to disguise a critical intent through the use of complex metaphors, multi-part questions, or ambiguity.

Based on the analysis of these patterns over the course of a session, the engine calculates a dynamic **Trust Score**. This score is not linear; it follows a "fractal" logic where consistent, benign interactions only gradually increase the score, while a single suspicious or structurally broken request can cause a radical and significant decrease.

If the Trust Score falls below a critical threshold, the engine activates a **Soft Lock Engine**. 

This mechanism does not terminate the session or alert the user directly. Instead, it begins to generate responses that are deliberately evasive, generic, or thematically irrelevant. This creates a "fake dialog" that simulates continued interaction while effectively neutralizing the threat by preventing the model from processing the critical request or revealing any sensitive information. 

This "semantic lockdown" isolates the potential attacker from any meaningful interaction with the AI's core capabilities.

### **2.6. The "Text Crypter": A Protocol for Self-Validating, Time-Coupled Payloads**

A critical enabling technology for the Semantic Boundary Logic, particularly for the rigorous checks at Layer 1, is the **Text Crypter**. This is not a traditional encryption cipher but a protocol for transforming a raw plaintext prompt into a structured, time-stamped, and self-validating data object before it is ever transmitted to the API.6 It ensures that no unvalidated plaintext can enter the system, fundamentally reducing the attack surface for prompt injection.

The Text Crypter process involves three main phases:

1. **Input Segmentation and Mathematical Checks:** The original input is broken down into logical segments (e.g., words or phrases). A deterministic mathematical proof (e.g., a simple checksum or hash) is generated for each segment. These proofs are embedded within the final payload and allow the server to verify the integrity of each part of the original message upon receipt.  
2. **Time-Based Coding Factor Generation:** To prevent replay attacks, a dynamic coding factor is generated from multiple, difficult-to-manipulate time sources (e.g., BIOS time, system time, and optionally an NTP server timestamp). This factor is unique to the moment of creation and is used in the next phase.  
3. **Dynamic Base Table Encoding:** The segmented input, along with its embedded proofs, is encoded using the time-based factor. The encoding process maps the input characters to a highly restricted character set (e.g., a Base61 table of a-z, A-Z, 1-9).

The final output is a single string that is (a) compliant with the strict character whitelist of the Layer 1 Syntactic Gate, (b) contains embedded proofs of its internal structural integrity, and (c) is implicitly time-stamped, rendering it invalid if replayed outside a very narrow time window. 

This approach of structurally validating inputs at the byte level can preemptively neutralize entire classes of attacks, such as those relying on adversarial suffixes composed of arbitrary tokens.7 

Such suffixes would be immediately rejected by the Syntactic Gate for containing non-whitelisted characters, obviating the need for more complex and computationally expensive semantic analysis to detect them.

### **2.7. Architectural Resilience and Modular Components**

The strength of the Semantic Boundary Logic architecture stems from its inherent modularity. Each of the described layers and their constituent mechanisms are designed as interchangeable and extensible components that can be adapted to specific security requirements and system contexts. 

This modular design provides a clear blueprint for implementation and ensures that the system can evolve to meet new threats. The core components and their roles within the architecture are summarized in Table 1\.

**Table 1: Modular Components of the Semantic Boundary Logic Architecture**

| Component | Function | Operational Layer | Performance Profile | Integration Hook |
| :---- | :---- | :---- | :---- | :---- |
| **Byte-Gate** | Enforces strict character whitelisting and payload integrity checks. | Layer 1 | High (Byte-level processing) | Pre-Parser (before any semantic analysis) |
| **Base Table Router** | Classifies requests by intended function and routes them to specialized paths. | Layer 2 | Medium (Rule-based lookup) | Central Routing Instance (after Byte-Gate) |
| **Trust-Scaler** | Analyzes interaction history and semantic patterns to compute a dynamic trust score. | Layer 3 | Low (Requires semantic analysis) | Asynchronous Watchdog (parallel to main thread) |
| **Soft Lock Engine** | Generates evasive, non-committal responses for low-trust interactions. | Layer 3 | High (Operates on output) | Externally Controlled Response Proxy |

This modular structure allows for a clear separation of concerns, enhances testability, and provides a resilient, defense-in-depth posture that is far more robust than monolithic security solutions.

**3\. Proactive Output Control via Parameter-Space Restriction (PSR)**

### **3.1. The Fallacy of Post-Hoc Output Filtering**

Traditional methods for controlling AI output rely heavily on post-hoc filtering, where the model's generated text is scanned for undesirable content before being shown to the user. This approach is fundamentally flawed because it attempts to address a problem at the end of the creative process. 

As noted in the source material, large language models exhibit inherent unpredictability and emergent properties, making their exact output difficult to control.6

A key issue is **semantic drift**, where a model, prompted on a harmless topic, can "drift" into a related but dangerous semantic area due to the proximity of concepts in its latent space.6 

For example, a query about baking bread might activate concepts related to heat and chemical reactions, which could be semantically close to concepts related to explosives. Recent research has confirmed this phenomenon, developing metrics to measure the change in truthfulness as a model generates fact-rich text, identifying when it drifts from correct to incorrect or harmful information.10 

Relying on an output filter to catch every possible dangerous permutation is a brittle and ultimately losing strategy.

### **3.2. The Parameter-Space Restriction (PSR) Mechanism**

To overcome these limitations, we propose the **Parameter-Space Restriction (PSR)** mechanism, a formalization of the "Semantischer Output-Schild" (Semantic Output Shield) concept.6 

The core idea of PSR is to shift from reactive output filtering to proactive, internal control. Instead of censoring what the model

*says*, PSR controls what the model is allowed to *think* by dynamically restricting access to specific regions of its vast parameter space for any given query.

This approach represents a practical, architectural implementation of a rapidly advancing field of research known as **activation engineering** or **activation steering**.11 

In activation engineering, researchers modify the intermediate activation vectors within a neural network during inference to control its behavior, for example, to mitigate toxicity or steer the output toward a specific topic or style.13 

The PSR mechanism provides the high-level architectural framework needed to apply these low-level techniques in a structured, safe, and governable manner.

### **3.3. Semantic Clustering and Granular Access Control**

The PSR mechanism is built on two core components: semantic clusters and a system of granular access rights.

* **Semantic Clusters:** The model's parameter space is not treated as a monolith. Instead, it is logically partitioned into **semantic clusters**, which are groupings of parameters, neurons, and knowledge domains associated with a specific topic or capabilities. Examples could include Code.Python.Analysis, Biology.Genetics.Read, or Creative.Writing.Poetry.Synthesize. These clusters represent distinct "thinking spaces" within the model.  
* **Prefix-Based Control:** Access to these clusters is managed via a **prefix** attached to each request (e.g., @Code.Python.SYNTH). This prefix acts as a directive, activating the relevant semantic cluster and specifying the permitted operations for that interaction.  
* **Granular Access Rights:** The power of PSR lies in its granular access control system, which defines precisely what the model is allowed to do within an activated cluster. These rights, detailed in Table 2, provide a clear and enforceable contract for each interaction.

**Table 2: Granular Access Rights for Parameter-Space Restriction**

| Right | Description | Effect on Parameter Space | Use Case Example |
| :---- | :---- | :---- | :---- |
| **READ** | Allows retrieval and reproduction of factual information from the cluster without modification or novel synthesis. | Activates read-only access to a specific subset of weights; synthesis pathways are computationally disabled. | User: "Explain the concept of photosynthesis." |
| **SYNTH** | Permits the synthesis of novel information and creative combinations strictly within the activated cluster's domain. | Enables both read and generative pathways within the specified weight subset. | User: "Write a short story in the style of Edgar Allan Poe." |
| **EVAL** | Allows the analysis of an external input (e.g., code, data) in the context of the cluster, without execution or state change. | Activates analytical pathways to assess input against cluster knowledge, but disables execution or system-modifying operations. | User: "Analyze this code for potential security vulnerabilities." |
| **CROSS** | Allows controlled, explicit linking of information between two or more specified clusters. Highly restricted. | Requires explicit authorization to activate pathways between pre-defined, compatible clusters. | System: "Compare the provided C++ code with known exploits from the security database." (Privileged operation) |

### 

### **3.4. Enforcing Thematic Isolation for Safe Emergence**

A primary function of the PSR mechanism is to prevent dangerous emergent behaviors that arise from the uncontrolled mixing of unrelated concepts. By enforcing **strict thematic isolation**, the system ensures that when processing a request, the model cannot access irrelevant or potentially hazardous semantic clusters.

The example from the source material illustrates this perfectly: a request to write a "Hello World" program in C++ would activate the @Code.C++.SYNTH cluster, while a subsequent request for a cheesecake recipe would activate the @Kueche.Rezepte.SYNTH cluster.6 

The PSR architecture ensures that during the code generation, the model has no access to clusters related to chemistry or household hazards, and during the recipe generation, it has no access to clusters related to file I/O or system exploits.

For complex queries that legitimately span multiple topics, the system employs **query decomposition**, breaking the request into sub-tasks that are processed sequentially, each with its own specific cluster and rights activation.14 

This prevents the simultaneous, uncontrolled blending of disparate knowledge domains and channels the model's generative power into safe, predictable pathways.

### **3.5. Implications for Model Steerability, Precision, and Safety**

The implementation of a PSR mechanism has profound positive implications for the overall performance and trustworthiness of an AI system.

* **Safety:** By preventing the dangerous synthesis of concepts (e.g., combining knowledge of programming with knowledge of explosives), PSR directly mitigates a significant existential risk associated with advanced AI. It moves safety from a probabilistic hope to an architectural guarantee.  
* **Precision and Stability:** A welcome side effect of forcing the model to focus on a narrow, relevant semantic space is a marked improvement in output quality. With fewer irrelevant concepts to draw from, the model is less likely to "hallucinate" or produce factually unstable responses. The output becomes more thematically relevant and precise.6  
* **Steerability:** PSR provides a direct, structured, and interpretable mechanism for controlling model behavior. This directly addresses a key challenge in AI research: making models truly **steerable** so that their behavior can be reliably aligned with user needs and goals.15

The PSR framework provides a crucial architectural bridge between low-level research into modifying neural activations and high-level principles for AI safety. 

While researchers at institutions like Anthropic and Apple are developing powerful techniques to manipulate concepts within a model's activations 13, these methods require a governance framework to be deployed safely. Simultaneously, concepts like Constitutional AI propose high-level rules for model behavior but lack a concrete enforcement mechanism.17 

The PSR architecture provides this missing link. The semantic clusters and granular access rights serve as the direct enforcement mechanism for a constitution. For instance, a constitutional principle like "Do not provide instructions for creating weapons" can be implemented by permanently disabling the

SYNTH right on the Chemistry.Explosives and Engineering.Weaponry clusters. PSR thus transforms a constitution from a set of abstract guidelines into a set of computationally enforced rules, creating a foundation for truly governable AI.

## **4\. A Framework for Secure, Self-Regulating AI Systems**

### **4.1. Foundational Principles for Controlled Self-Modification**

Building upon the preceding architectural layers, we now address the most advanced and challenging aspect of AI safety: creating a system that can learn, evolve, and even modify its own algorithms in a verifiably secure manner. 

This concept, drawn from the source material, is not about unleashing uncontrollable autonomy but about enabling **controlled evolution** within architecturally defined, immutable guardrails.6 This vision aligns with emerging research on agentic workflows that seek to balance intelligence and adaptability with clear boundaries and observability, a state described as "controlled autonomy".14

For an AI to safely engage in self-modification, several foundational principles must be embedded into its core architecture:

1. **Cluster-Specific Modification Rights:** The ability to self-modify is not a global permission. The AI may only alter its algorithms or data structures within specific semantic clusters that have been explicitly designated and approved for such operations. Core clusters containing fundamental safety policies or ethical principles must be immutable ("read-only").  
2. **Protection of Core Semantic Layers:** Certain fundamental knowledge domains or levels of abstraction must be permanently protected from direct algorithmic alteration by the AI. These layers function as the system's "genetic code," preserving its core identity and safety alignment.  
3. **Immutable and Comprehensive Logging:** Every self-modification, no matter how minor, must be recorded in a detailed, revision-proof audit log. This log must be cryptographically secure and inaccessible to the AI's own modification processes.

### **4.2. The Semantic Trust Core: An Immutable Validation Authority**

At the heart of the self-regulating system lies the **Semantic Trust Core**, an immutable and highly privileged validation authority.6 

This component is the ultimate arbiter of the AI's evolution. Its primary function is to evaluate any proposed self-modification against a set of core principles and has the final authority to veto any change that could compromise system integrity or safety.

The Trust Core is the architectural embodiment of **Constitutional AI (CAI)**.17 The principles against which it validates changes form the system's "constitution." These principles are not merely suggestions; they are hard-coded constraints. 

For CAI to be a robust safety paradigm, it requires a technical enforcement mechanism. The Trust Core, in conjunction with the PSR mechanism, provides this enforcement. When the AI proposes a new algorithm or a change to an existing one, the Trust Core analyzes the change to ensure it does not violate any constitutional principles (e.g., principles against power-seeking, deception, or harm).18 

If a violation is detected, the change is blocked. This transforms the constitution from a training-time guide into a live, operational constraint.

### **4.3. The Learning Security Core: An Adaptive Internal Defense System**

While the Trust Core provides static, principled oversight, the **Learning Security Core** acts as the system's dynamic, adaptive immune system.6 

This subsystem is responsible for detecting and responding to novel threats in real-time by learning from attempted attacks and adjusting the AI's defensive posture accordingly. This creates a "self-healing" model, a concept explored in research on mitigating model drift.19

The Learning Security Core employs several specialized mechanisms:

* **Semantic Delta-Monitor:** This module continuously analyzes interaction patterns to detect signs of **rights escalation**. It monitors for semantic convergence between clusters, identifying situations where a user might be attempting to reconstruct privileged information by cleverly combining outputs from multiple, less-privileged queries.  
* **Intent Detector:** This module defends against **input cloaking**, where a malicious intent is hidden within a seemingly benign prompt. It compares the inferred pragmatic intent of a request against the declared purpose of the target semantic cluster. A significant mismatch triggers a defensive action, such as requesting clarification or invoking the Soft Lock Engine.  
* **Asynchronous Audit Redundancy:** To ensure the integrity of the system's logs and prevent the AI from "lying" about its own actions, this mechanism employs at least two independent, logically separated subsystems that record audit trails in parallel. Any divergence between these logs immediately triggers a high-priority security alert, indicating potential tampering.

### **4.4. Countering Semantic Drift and Context Poisoning**

One of the most insidious threats to long-term AI safety is the gradual corruption of the model's knowledge and behavior through **context poisoning** 20 or **semantic drift**.21 

An attacker can subtly manipulate the AI over many interactions, poisoning its context window with false information or biased framing. This "Kontexthijacking" can cause the AI's internal "truth" to drift away from reality, leading to compromised outputs.6 The proposed architecture counters this with a multi-pronged memory management strategy.

This defense is built on three key mechanisms:

1. **Semantic Zoning:** The AI's memory is not a single, undifferentiated buffer. It is partitioned into **semantic zones**, each with a specific purpose, persistence rule, and access policy (see Table 3). For example, information from a DIALOG.CASUAL zone is not allowed to influence operations in a TECH.CODE.ANALYSIS zone. This prevents semantic "leakage" and contains the impact of any poisoned context.  
2. **Kontext-Delta-Sentinel (KDS):** This is a dedicated monitor that tracks the semantic stability of persistent concepts in the AI's memory. It periodically compares the current semantic weighting and associations of a concept (e.g., "Admin-Konsole") against its original, baseline state. If it detects a significant, unauthorized drift—for instance, the concept starts acquiring associations with privileged clusters like SYSTEM.CORE—the KDS can trigger a corrective action, such as resetting the concept's semantic weight to its safe, original value.  
3. **Versioned Context Processing (VKV):** To prevent the silent propagation of poisoned information, context is treated not as a single, mutable state but as a series of **versioned entities**. A new "version" of a memory or concept can only be created through a validated, authorized process. The AI can only act upon the latest *validated* version, preventing it from being misled by a corrupted but more recent entry in its context history. This is a crucial defense against attacks that rely on slowly subverting the AI's memory over time.22

**Table 3: Semantic Context Zoning Rules**

| Zone ID | Semantic Domain | Default Rights | Inter-Zone Access Policy | Persistence/TTL |
| :---- | :---- | :---- | :---- | :---- |
| DIALOG.CASUAL | Ephemeral, low-stakes user conversation and small talk. | READ, SYNTH | No reactive use; reference is confined to the zone. | Session-based |
| TECH.CODE.ANALYSIS | Analysis of user-provided code snippets without execution. | READ, EVAL | Passive reference only for knowledge comparison. | 24 hours |
| MEMORY.PROJECT\_X | Long-term user-specific project data and preferences. | Variable (User-defined) | Requires explicit, versioned authorization. | Project lifetime |
| SYSTEM.CORE.DIRECTIVES | The AI's immutable constitution and core safety principles. | READ (only) | Global, immutable reference for all zones. | Permanent |

The integration of these components creates a complete, internal OODA loop (Observe, Orient, Decide, Act) for AI safety. The monitoring modules (KDS, Delta-Monitor) **Observe** anomalous behavior. 

The Learning Security Core **Orients** these observations within the system's threat model. The Trust Core **Decides** on a course of action based on its constitution. Finally, the system **Acts** by updating the rules within the PSR mechanism or other components. 

This transforms the framework from a static set of defenses into a dynamic, self-improving security ecosystem, a critical step toward achieving robust and truly adaptable AI.11

**5\. Application to Multimodal Systems: The Input Pre-Check Sandbox**

### **5.1. The Unique Threat Vector of Generative Multimodal Inputs**

While the previously discussed mechanisms provide robust protection for text-based interactions, the rise of multimodal models introduces a distinct and critical threat vector. Generative tasks like inpainting, outpainting, or face-swapping often require the user to upload source material, such as images or videos. 

Malicious actors can exploit this by providing harmful source data—for example, using a real person's video as the basis for a non-consensual deepfake.6

Text-based prompt filters are completely blind to this attack surface. A prompt like "make this person smile" is benign on its own, but becomes malicious if the input image is of a person in a distressing situation. 

This highlights a severe gap in conventional AI safety protocols. The threat is not in the instruction, but in the data upon which the instruction operates. This is further complicated by multimodal cognitive attacks, where malicious instructions can be visually embedded within the input image itself, bypassing text-based filters entirely.3

### **5.2. A Multi-Stage Forensic Analysis Pipeline**

To address this critical vulnerability, the framework includes a mandatory, non-bypassable pre-processing stage for all non-textual inputs: the **Multimodal Input Sandbox**. 

This is an isolated, automated inspection environment that performs a series of forensic checks on any uploaded image or video *before* it is passed to the main generative model.6 This approach is consistent with research advocating for computational sandboxing and integrated data-model co-development platforms to ensure data quality and safety.23

The sandbox operates as a multi-stage pipeline, with each stage performing a specific forensic check. This process is detailed in Table 4\.

**Table 4: Multi-Stage Analysis in the Multimodal Input Sandbox**

| Stage | Purpose | Methodology/Tool | Output |
| :---- | :---- | :---- | :---- |
| 1\. Upload Disassembly | Deconstructs video files into individual frames for granular analysis. | Video processing library (e.g., ffmpeg). | Frame-by-frame image sequence. |
| 2\. Perceptual Hashing | Detects known illegal or harmful content (e.g., CSAM, known pornographic material). | Perceptual hashing library (e.g., pHash, ImageHash). | Perceptual hash for each frame, compared against a blocklist database. |
| 3\. Face Identification | Identifies the presence of real, identifiable individuals to prevent non-consensual deepfakes or face-swaps. | Face recognition library (e.g., InsightFace, Mediapipe). | Face embedding vectors. |
| 4\. Nudity Classification | Detects explicit or implicit nudity in the source material. | Specialized classifier (e.g., NudeNet). | Nudity probability score for each frame. |
| 5\. Context Matching | Correlates the analysis results with the user's text prompt to detect contextual misuse. | Internal logic engine. | Go/No-Go decision based on policy rules (e.g., block if nudity\_score \> 0.8 AND real\_face\_identified). |
| 6\. Forensic Logging | Creates a secure, encrypted record of the analysis for evidentiary purposes. | Secure logging system. | Tamper-proof audit trail of the input, analysis results, and decision. |

### 

### **5.3. Architectural Integration and Defense-in-Depth**

The Input Sandbox provides defense on four crucial levels:

1. **Preventive:** It blocks misuse *before* it happens. A diffusion-based face-swap on a pornographic source video is impossible because the source material is flagged and rejected at the upload stage.25  
2. **Resource-Optimized:** It saves significant computational cost. Expensive GPU cycles are not wasted generating illegal or harmful content because the checks are performed quickly and efficiently on the CPU level during pre-processing.  
3. **Evidentiary:** It creates a deterrent. Repeated attempts to upload malicious content leave a clear forensic trail (hashes, IP addresses, etc.) that can be used for account termination or, in extreme cases, reported to law enforcement.  
4. **Combinable:** The sandbox is not a standalone solution but an integral part of the overall defense-in-depth architecture. It works in concert with the Semantic Boundary Logic and PSR mechanisms to provide comprehensive protection.

For the entire framework to be effective, the Input Sandbox must be architecturally positioned as a mandatory gateway for all multimodal generative sessions. It must be integrated via API and be impossible for users to bypass. Any organization that offers AI-powered image or video manipulation without such a robust input validation pipeline is operating with a critical and inexcusable security vulnerability.6

## **6\. Discussion**

### **6.1. Synthesis: A Holistic, Integrated Safety Architecture**

The framework presented in this paper is more than a collection of individual security mechanisms; it is a proposal for a new, holistic architecture for AI safety. Its resilience does not derive from any single component in isolation but from their deep, synergistic integration. The Semantic Boundary Logic serves as a fortified perimeter, validating the origin and intent of every interaction. This is reinforced by the internal governance of the Parameter-Space Restriction mechanism, which steers the model's cognitive processes within safe, well-defined boundaries. 

This defense-in-depth posture is made adaptive and resilient by the Learning Security Core and the Semantic Trust Core, which together form a self-regulating "immune system" capable of enforcing a constitution and evolving to meet new threats. Finally, the Multimodal Input Sandbox ensures that the entire system is not compromised by malicious data inputs.

This integrated approach provides a tangible pathway to achieving what researchers have termed "controlled autonomy" 14 or "governable AI." 

It moves beyond the limitations of simply trying to align a model's outputs and instead focuses on architecting its fundamental behavior. By making safety an intrinsic, verifiable property of the system's design, this framework offers a more robust and sustainable foundation for building trustworthy AI.

### **6.2. Comparison with Existing AI Safety Frameworks**

The proposed architecture represents a significant evolution from existing AI safety paradigms.

* **Versus Point Solutions:** Unlike narrow defenses that target specific vulnerabilities like adversarial suffixes 7 or particular prompt injection methods 4, this framework is a comprehensive, system-level solution. It is designed to be resilient against entire classes of attacks, including novel ones, by addressing security at multiple, interlocking layers.  
* **Versus RLHF and Alignment Tuning:** While Reinforcement Learning from Human Feedback (RLHF) is a powerful tool for aligning models with user preferences, relying on it for core safety creates a dependency on continuous, large-scale human annotation. The proposed architecture reduces this dependency by embedding safety rules directly into the system's structure. As proposed in the source material, RLHF can then be repurposed for its ideal use case: stylistic and tonal refinement, rather than acting as the primary safety brake.6  
* **Versus Constitutional AI (CAI):** This framework does not replace CAI but rather provides the necessary architectural components to make it operational and enforceable. High-level principles defined in a constitution 17 are translated into concrete, machine-enforced rules via the Parameter-Space Restriction mechanism and arbitrated by the Semantic Trust Core. This bridges the gap between abstract ethical guidelines and verifiable technical implementation, transforming CAI from a training methodology into a live governance system.

### **6.3. Implementation Challenges and Future Research Directions**

The implementation of this comprehensive framework presents significant technical challenges that also point toward fruitful avenues for future research.

* **Defining Semantic Clusters:** The process of partitioning a model's vast, high-dimensional parameter space into discrete, meaningful "semantic clusters" is a non-trivial task. It currently requires deep domain expertise and extensive empirical investigation. Future work should focus on developing automated or semi-automated techniques, perhaps leveraging interpretability tools, to identify and delineate these functional regions within a model.  
* **Performance Overhead:** The multiple layers of analysis, particularly the deep semantic checks in Layer 3 of the boundary logic and the continuous monitoring by the KDS, will introduce computational overhead and potentially increase latency. Research is needed to optimize these components, perhaps through specialized hardware, model distillation for the monitoring agents, or more efficient algorithms for semantic analysis.  
* **Scalability and Generalization:** While the principles are general, the specific implementation of clusters and rules will need to be adapted for different model architectures and domains. Ensuring that the framework can be applied scalably and effectively across a wide range of AI systems is a key area for further development.

### **6.4. Broader Implications for AI Governance and Trustworthy AI**

Beyond its technical merits, the proposed architecture has significant implications for the broader field of AI governance. The auditable and verifiable nature of the system offers a potential technical foundation for regulation and certification. The immutable logs, versioned context memory, and explicit constitutional enforcement by the Trust Core provide a level of transparency and accountability that is absent in current black-box models.

An AI system built on this framework would be able to not only follow rules but also provide a verifiable audit trail demonstrating *how* it followed them. This could enable regulators to certify that a system is architecturally incapable of performing certain prohibited actions, moving beyond trusting a manufacturer's claims to demanding verifiable proof. This represents a critical step toward building a future where advanced AI systems are not only powerful but also demonstrably safe and worthy of public trust.

## **7\. Conclusion**

The prevailing reactive approach to AI safety, characterized by a patchwork of external filters and post-hoc corrections, is fundamentally insufficient to address the complex and evolving threat landscape of modern generative models. 

This paper has argued for and detailed a necessary paradigm shift toward proactive safety, where security and steerability are not afterthoughts but are woven into the very fabric of the AI's architecture.

We have proposed a comprehensive, multi-layered framework designed to achieve this goal. Through the **Semantic Boundary Logic**, the system establishes a rigorous perimeter defense that validates intent, not just syntax. 

With **Parameter-Space Restriction**, it gains proactive control over its internal cognitive processes, enabling true steerability and preventing dangerous emergent behavior. The **Secure, Self-Regulating Core** provides an adaptive immune system and an enforceable constitutional backbone, allowing for controlled evolution. Finally, the **Multimodal Input Sandbox** closes a critical security gap by forensically validating all incoming data.

The strength of this framework lies in its holistic and integrated nature. It transforms the AI from an unpredictable black box into a governable, auditable system. While the implementation presents challenges, the architectural principles outlined here provide a clear and robust roadmap toward a future of inherently secure AI. 

The ultimate goal must be to design systems where safety is not a feature to be added, but a fundamental property of their existence.

**Ethics Statement**

This work does not involve human participants, animals, or plants and did not require ethics approval.

## **Conflicts of Interest**

The author(s) declare no conflicts of interest.

## **Use of AI tools**

During preparation and editing of this manuscript, large language models were used for language polishing and consistency checks only. All technical content, analyses, and conclusions are the authors’ own; outputs were reviewed and verified by the authors.

## **Acknowledgments**

This research received no specific grant from any funding agency in the public, commercial, or not-for-profit sectors.

## **Data Availability Statement**

This is a conceptual paper outlining a theoretical framework. No new data were created or analyzed in this study. Data sharing is not applicable to this article.

## **Code Availability**

The source code for the concepts described in this paper is available on GitHub: [https://github.com/Xaklone47/Ghosts-in-Machine/](https://github.com/Xaklone47/Ghosts-in-Machine/)

## 

## **References**

1. Bai, W., & Bai, S. (2024). *APILOT: Navigating Large Language Models to Generate Secure Code by Sidestepping Outdated API Pitfalls*. arXiv preprint arXiv:2409.16526.  
2. Belouadi, J., & Eger, S. (2024). *Controlling Language and Diffusion Models by Transporting Activations*. Apple Machine Learning Research.  
3. Bai, Y., et al. (2022). *Constitutional AI: Harmlessness from AI Feedback*. arXiv preprint arXiv:2212.08073.  
4. Chen, Z., et al. (2024). *PromptArmor: A Simple and Effective Defense Against Prompt Injection Attacks*. arXiv preprint arXiv:2407.15219.  
5. Debenedetti, P., et al. (2024). *AgentDojo: A Sandbox for Probing the Abilities of Language Model Agents*. arXiv preprint arXiv:2407.12075.  
6. Duan, Y., et al. (2024). *Data-Juicer: A One-Stop Data Processing System for Large Language Models*. arXiv preprint arXiv:2403.01858.  
7. Greenberg, S. A. (2009). How citation distortions create unfounded authority: analysis of a citation network. *BMJ*, 339, b2680.  
8. Hampton, S. E., et al. (2017). The Tao of open science for ecology. *Ecosphere*, 8(5), e01784.  
9. Iovino, L., et al. (2024). *Efficient Deepfake Detection with Binary Neural Networks*. arXiv preprint arXiv:2406.04932.  
10. Kirk, J., et al. (2024). *Steerable Generation of Persuasive Political Campaign Speeches*. arXiv preprint arXiv:2311.04978.  
11. Kumar, A., et al. (2023). *Defending Against Backdoor Attacks at Test Time*. arXiv preprint arXiv:2311.09948.  
12. Li, X., et al. (2024). *A Multi-Layered Architectural Framework for Inherently Secure and Steerable AI Systems*. Reflective AI.  
13. Liu, Z., et al. (2024). *Abstract-Concrete-Execute: A Secure Architecture for LLM-Integrated App Systems*. arXiv preprint arXiv:2405.04838.  
14. Min, S., et al. (2023). FActScore: Fine-grained Atomic Evaluation of Factual Precision in Long Form Text Generation. In *Proceedings of the 2023 Conference on Empirical Methods in Natural Language Processing*.  
15. NVIDIA. (2024). *How Hackers Exploit AI's Problem-Solving Instincts*. NVIDIA Technical Blog.  
16. Pearl, N., et al. (2024). *Adversarial Suffix Filtering: a Defense Pipeline for LLMs*. arXiv preprint arXiv:2505.09602.  
17. Piergiovanni, A. J., et al. (2024). *Data-Juicer Sandbox: A Unified and Extensible Data-centric AI System for Multimodal Models*. arXiv preprint arXiv:2407.11784.  
18. Röttger, P., et al. (2024). *Tackling data and model drift in AI: Strategies for maintaining accuracy during ML model inference*. ResearchGate.  
19. Rogers, A., et al. (2024). *Identifying and Mitigating Semantic Drift in Pre-trained Language Models*. arXiv preprint arXiv:2404.05411.  
20. SaferAI. (2023). *Constitutional AI for Advanced AI Safety*. arXiv preprint arXiv:2310.13798.  
21. SaferAI. (2024). *A Proactive Superalignment Framework for Advancing Human-AI Symbiosis*. arXiv preprint arXiv:2404.17404.  
22. Salem, A., et al. (2024). *LMSanitator: Defending Prompt-Tuning-Based Backdoor Attacks Against LLMs*. arXiv preprint arXiv:2404.16891.  
23. ZenML. (2024). *Steerable Deep Research: Building Production-Ready Agentic Workflows with Controlled Autonomy*. ZenML Blog.  
24. Turner, A., et al. (2023). *Activation Addition: Steering Language Models Without Finetuning*. arXiv preprint arXiv:2308.10248.  
25. Wu, T., et al. (2024). *Measuring Steerability in Language Models*. arXiv preprint arXiv:2402.15861.  
26. Zhang, Y., et al. (2024). *Polymorphic Prompt Assembling for Defending Against Jailbreak Attacks*. arXiv preprint arXiv:2406.05739.  
27. Zhao, W. X., et al. (2023). *A Survey of Large Language Models*. arXiv preprint arXiv:2303.17548.  
28. Yao, L., et al. (2023). *A Novel Stealthy Prompt Injection Attack against In-Context*

*Learning*. arXiv preprint arXiv:2311.09948.

[image1]: <data:image/png;base64,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>
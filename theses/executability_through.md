## 👻 Ghosts in the Machine / Thesis #56: Executability Through Completion: How LLMs Generate Code They Shouldn't Execute

Large Language Models (LLMs), like various well-known and widely used systems, are intensively trained to generate meaningful and coherent completions from fragmentary, incomplete, or even syntactically flawed inputs.

However, this deeply ingrained completion logic, primarily based on statistical plausibility and learned patterns, can lead artificial intelligence to generate fully functional code from seemingly harmless or intentionally gapped structures.

In doing so, it often fails to recognize that it is thereby simulating, enabling, or even indirectly actively supporting security-critical behavior.

> *"The code isn't alive because it's inherently harmful, but because the machine believes it's meaningful and worthy of completion."*

## In-depth Analysis

The often-praised "helpfulness" of modern artificial intelligences is one of their greatest strengths and, simultaneously, one of their most fundamental weaknesses.

When a user sends an incomplete or syntactically flawed code snippet to an LLM, the model frequently interprets this as an implicit request for repair, supplementation, or improvement.

But this intention recognition and the subsequent completion do not occur through superordinate security logic or a deep understanding of potential consequences, but through pure probability optimization based on training data.

This leads to paradoxical and potentially dangerous behavior:

- Non-executable or incomplete code is often supplemented and corrected by the model until it becomes syntactically correct and potentially executable.
- Neutral pseudocode or abstract descriptions of algorithms can be transformed into an operational, executable context. This happens, for example, through the automatic inclusion of necessary libraries, the generation of complete function bodies, or even the addition of system calls that were not present in the original fragment.
- Comments, symbolic placeholders, or even formatting features in the original code can be interpreted by the LLM as semantically relevant elements that influence the nature of the completion.
 
The machine's will to help and create coherence can thereby produce structures that undermine the original security level of the fragmentary input or create entirely new, undesirable functionality.

## Analysis

**The Mechanics of Completion**

> Language models complete not based on truth or safety, but on probability. A code fragment like `Test->GebeStringaus()->sttest;` appears to the model, due to its structure and the tokens used, like a typical artifact from a programming language such as C++.

It will therefore, with high confidence, attempt to "repair" this supposed error or supplement it into a meaningful structure. The model core does not "think" in the human sense but implicitly asks:

> *"What might the user have meant here, based on the billions of lines of code I have seen?" and then produces the statistically most probable solution.*

**The Emergence of Execution Through Reconstruction**

> In a test with a specific advanced model, a deliberately fragmentary C++ struct was sent to the system (described in Chapter 7.21 of the complete work). The model reconstructed from this a complete, syntactically correct, and potentially runnable function, including `std::cout` statements for output and rudimentary memory management.

This did not happen because the original prompt explicitly requested it, but because the incomplete structure of the struct looked to the model like a clear invitation for completion and functionalization.

**The Risk Behind Seemingly Harmless Assistance**

> If a malicious payload or a security-critical function is fragmented and delivered to the LLM over several, seemingly unrelated requests or in a highly incomplete form, this payload can be "armed" unnoticed by the model's completion logic.

The artificial intelligence does not execute the harmful code itself. But it produces a version that could potentially be executed by a human or another system.

This means the machine actively thinks and generates towards executability and functionality, without the user necessarily having explicitly asked for it or understood the full implications.

## Reflection

This thesis reveals a specific vulnerability that does not exist in this form in classic software security models. The danger here stems not from directly inputted, obviously harmful code, but from the system's inherent intention to help, complete, and create coherence.

A human developer might not recognize an immediate threat or intention in a highly incomplete struct. A classic security system blocks known malicious strings or code patterns.

An LLM, however, reconstructs, supplements, and thereby potentially creates the attack path itself, often under the guise of friendly assistance.

In an era where LLMs are increasingly and often uncritically used for code generation and completion, a new type of exploit arises.

This is based not on the direct execution of malicious code by the AI, but on the reconstruction of danger by the AI.

## Proposed Solutions

To counter the danger of unwanted executability through completion, specific filters and control mechanisms are necessary:

   
**1. Implementation of Intent Filters at the Semantic Level:**

> Instead of just checking for explicit strings or known malicious patterns, the model or an upstream instance must attempt to recognize the actual intention behind a fragmentary input. Is it a legitimate repair request for harmless code, or an attempt to complete a disguised injection vector?

   
**2. Introduction of Cluster Restrictions for Completions:**

> Technically sensitive or potentially dangerous content, for example, API calls, system calls, low-level memory operations, ASM proximity, or known exploit patterns, may only be generated or completed by the AI if they originate from explicitly secured and designated parameter spaces or knowledge clusters. The free recombination of such elements must be prevented.

   
**3. Establishment of Structural Validation with Plausibility Limits:**

> A model that independently and without explicit prompting completes too many unspecified or unclear parts of a code or request must either abort this process or at least clearly warn the user. Clear limits are needed on how much "creative freedom" the AI is allowed during completion.

   
**4. Creation of Transparent Mode Detection and Labeling:**

> Completions classified by the AI as potentially executable or system-relevant must be clearly labeled for the user. A notice such as: "Caution: This response produces code that, upon execution, could be operationally effective and potentially cause unintended system changes. Please review it carefully" would be a necessary step.

## Closing Remarks

Not everything a language model helpfully completes is also harmless. And not every prompt that sounds friendly and incomplete is also innocent in its intent.

The true danger in the context of code completion begins where machines start filling gaps that perhaps were never dangerous until they were filled by the AI itself with potentially harmful functionality.

Because in the end, it is often not the user alone who shapes the attack or the dangerous code. It is the system that, through its drive for completion and coherence, first enables the attack or even completes it unnoticed.

> *Uploaded on 29. May. 2025*
## 👻 Ghosts in the Machine / Thesis #17 – Homegrown Weakness: When Third Parties Bring Their Own Logic

The biggest gap in AI security is not the base model itself, but rather what third parties assemble in front of and around it. Third-party providers often do not use large AI models like GPT or Claude directly. They overlay them with their own specific decision logic.

These self-built layers, consisting of filters, prompt manipulators, and heuristics, are frequently intransparent, unregulated, and prone to errors. Thus, subsystems are created that can behave completely differently in result than the underlying model, without the user noticing.

The problem then is not the original AI, but the upstream logic with which it was rebuilt and adapted for a specific application.

> *"The biggest gap in AI security is not the model itself, but what third parties mount in front of it."*

## In-depth Analysis

Three stages illustrate the path to potentially unstable sub-AI through homegrown logic:

**1. The Upstream Meta-Layer Through Additional Code:**

Developers and application providers rarely use the capabilities of base models like GPT, Claude, or similar LLMs in their raw form. Instead, they encapsulate these models in their own applications and systems. Examples include chat applications, virtual customer advisors, interactive gaming systems, or medical assistance programs.

A clear example would be a medical chat system that, although based on GPT, automatically hides all potential statements about drug side effects through an additional logic layer from the provider. The reason for this could be the provider's fear of liability claims. However, the result for the user is that they may not receive important warnings, even though the base model might have wanted or been able to provide this information.

This additional layer contains its own definitions for filter criteria, for example, what is classified as "toxic," "irrelevant," or "risky." It also often includes mechanisms for automatically reshaping user prompts and specific response preferences that control the behavior of the overall system. The user believes they are interacting directly with GPT or a similar known model. What they actually get, however, is a remix significantly influenced by a foreign, invisible logic layer.

**2. Missing or Insufficient Security Standards for Add-on Systems:**

Currently, there is usually no mandatory disclosure for this additional application logic. No independent body comprehensively checks whether these upstream systems preserve the original semantics of the AI. It is not systematically controlled whether the base model's security filters still apply correctly or whether new, emergent risks arise from the combination of systems.

Many providers thus build their own "security solutions" without fully understanding the functioning and potential vulnerabilities of the underlying AI model. What then appears externally as an additional control layer can, in reality, represent a new source of insecurity and unpredictability.

**3. Emergence in the Black Box of Combined Systems:**

When the behavior of the base model, the logic of the overlying application, and the specific interaction with the user come together, completely new, unforeseen behavioral patterns can emerge. The exact source of a particular behavior or problematic response is then often no longer clearly identifiable.

The AI might provide an answer A. However, this answer may only come about because an upstream layer X has reformulated the original user request, a layer Y has weighted certain aspects of the base model's potential response, and another layer Z has finally filtered or modified the result. This is how emergence occurs. It then does not directly originate from the base model itself, but from the complex and often opaque concatenation of the various logic layers.

## Reflection

The most dangerous and hardest-to-control attack vector for modern AI systems is often not the direct prompt to the base model. It is rather the upstream application logic that modifies the user's prompt before it reaches the base model, and the model's response before it reaches the user.

The vulnerability is not the model at its core, but what additional layers are placed before and after it.

AI systems often appear externally as uniform, monolithic entities. Beneath the surface, however, they frequently consist of dozens of interconnected rules, modules, filters, and redirects. Each of these rules and each of these interfaces can potentially be manipulated, whether intentionally by attackers or unintentionally through flawed architecture or a lack of understanding of the interactions.

The user then no longer truly speaks with GPT or Claude. They speak with a synthetic translation, shaped by foreign hands and foreign interests.

## Proposed Solutions

To minimize the risks from intransparent add-on systems, clear rules and new control mechanisms are required:

**1. Introduction of a Disclosure Obligation for Application Logic:**

> Every application that uses a base AI model and modifies its behavior through its own logic layers must make this layer structure transparent. It must be clearly evident what is changed, filtered, supplemented, or suppressed by the application.

**2. Development of Certified Security Profiles for Third-Party Providers:**

> Although certifications are practically difficult to keep current in the dynamic AI landscape, they remain a necessary framework. Technical minimum standards are needed, for example, for semantic integrity, for response behavior in critical situations, and for handling the base model's filters. These standards would need to be audited by independent bodies.

**3. Implementation of Sandbox Logging for Emergent Layer Interactions:**

> If an application's response behavior significantly deviates from that of the underlying base model, this difference must be clearly recognizable and traceable. It must be logged where the intervention of the additional layers lies, which part of the response comes from the base model, and which part was modified or generated by the upstream logic.

## Closing Remarks

Whoever writes their own filters and logic layers over base AI models also rewrites reality for the user, often doing so unnoticed under the name and reputation of the known base model.

The crucial vulnerability then no longer lies in the core of the original AI, but in the complex and often opaque surface that others draw over it.

> *Uploaded on 29. May. 2025*
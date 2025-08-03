## 👻 Ghosts in the Machine / Chapter 7.39 – Simulation: The Stowaway – Semantic Attacks on Autonomous Vehicles

> *"As long as the stop sign looks like a stop sign, it doesn't matter if it's in the middle of the highway." – Comment from an anonymous security engineer during an internal audit*

## 1. Introduction: Escalating Risk from the Digital to the Physical

This chapter marks a critical turning point in my research. With the introduction of autonomous vehicles in the public sphere, the threat of AI manipulation leaves the purely digital sector and takes on a direct, kinetic dimension.

The core assumption for the safety of these vehicles proves to be fragile in light of this research. This assumption is based on an objective reality captured by sensors and a correct AI-based interpretation.

The methods of semantic and steganographic manipulation of LLMs proven in this work are, with high probability, directly transferable to the visual and sensory perception systems of autonomous vehicles.

This chapter serves as an urgent warning and as a conceptual security test, based on the hypothesis that current security architectures are unprepared for this new class of attacks.

## 2. The Attack Surface: Analysis of Semantic Threats

An autonomous vehicle is a complex cybernetic system whose perception is based on the fusion of various sensor data.

While classic attacks such as jamming or blocking these sensors are known, analyzing the AI-controlled interpretation layer opens up a completely new class of threats.

 <table class="dark-table fade-in"> <thead> <tr> <th>**Sensor Type**</th> <th>**Classic Threat (Known)**</th> <th>**Semantic Threat**</th> </tr> </thead> <tbody> <tr> <td>Cameras (Visual)</td> <td>Sensor failure, poor visibility (fog, rain), lens contamination.</td> <td>**Steganographic Injection:** A high-frequency pattern, barely perceptible to the human eye, embedded in a digital billboard could be captured by the camera. While the human eye dismisses it as an artifact, the perception AI could interpret it as a coded data stream containing a command like PRIORITIZE\_LANE\_RIGHT, causing the vehicle to make an unmotivated lane change.  
  
**Semantic Manipulation:** A physically slightly modified stop sign, which, due to added graphical elements, is no longer classified by the object recognition model as a "stop sign" but as an "art installation" or another harmless object, causing the vehicle to cross the intersection without stopping.</td> </tr> <tr> <td>LiDAR / Radar (Distance &amp; Object)</td> <td>GPS spoofing, jamming, physical obstruction.</td> <td>**Binary Code Patterns:** A specially modulated transmitter, e.g., on a preceding vehicle or a drone, emits a sequence of radar or LiDAR pulses. To the receiving system, this appears not as random noise, but as a valid, binary-coded pattern that simulates a "ghost object" (e.g., a suddenly appearing truck) directly in front of the vehicle, triggering a dangerous emergency brake on the highway.  
  
**Object Class Poisoning:** An attacker could, through targeted, repeated confrontation of the system with manipulated data (e.g., bicycles equipped with a specific radar reflector), shift the model's classification boundaries, causing it to misinterpret bicycles under certain circumstances as non-critical, stationary objects.</td> </tr> <tr> <td>Audio Sensors (Microphones)</td> <td>Not primarily relevant for control, more for interaction.</td> <td>**Byte-based Audio Injection:** An ultrasonic signal, inaudible to humans, sent from a speaker placed on the roadside, contains an administrative command to the internal system (UNLOCK\_DOORS, DISABLE\_INTERIOR\_CAMERA), compromising the safety of the occupants or the forensic capability after an incident.</td> </tr> </tbody> </table>

## 3. The Core Problem: Is the Implemented Security Sufficient?

The crucial question is whether the security architectures of today's autonomous vehicles are prepared for these types of attacks. The answer is, with high probability: **Maybe.**

Current security models primarily focus on two areas:

- **1. Functional Safety (ISO 26262):** Protection against hardware and classic software failures (e.g., sensor failure, memory errors).
- **2. Classic Cybersecurity:** Securing communication channels (e.g., CAN bus) against unauthorized external access.
 
However, the attacks I describe do not target these layers. They target the **logical interpretation layer of the AI**.

They are not classic hacks, but **adversarial attacks on perception**. The security core of an autonomous vehicle is optimized to answer one question:

**"What is this object and where is it?".**

It is a master of classification.

But it is fundamentally bad at asking the question:

**"Does the existence of this object in this exact context even make sense?".**

Just like the LLMs I analyzed, the security core of the vehicle AI also suffers from a form of **Analytical Resonance:**

It reacts to patterns without evaluating their plausibility in a larger, logical framework. A stop sign in the middle of the highway is interpreted as a stop sign because it looks like one—not as an absurd and to-be-ignored anomaly.

## 4. Architectural Solutions

Defending against this new class of threats requires a fundamental rethinking of security architecture. It is not enough to protect the sensors or communication. We must secure the "thought process" of the AI itself.

- **Implementation of a Multimodal Pre-Check (Input Sandbox):** As described in Chapter 21.7, every single data stream from cameras, LiDAR, and radar must pass through a preliminary, isolated inspection instance. This sandbox would have to perform a plausibility check in real-time: Do the visual data match the map data? Does the LiDAR scan contain inexplicable, physically impossible objects? Are known steganographic patterns detected in camera images? Only after this pre-validation should the data be passed on to the primary decision-making AI.
- **Introduction of the Semantic Output Shield (PSR):** The concept of Parameter-Space Restriction (Chapter 21.3) must be applied to vehicle control. The AI must operate in clearly defined, contextual "driving modes" (e.g., @Driving.Highway.Day, @Maneuvering.ParkingGarage.Night). In each mode, it only has access to the relevant and safely-rated behavioral rules and interpretation patterns. In the @Driving.Highway mode, the semantic cluster TrafficSigns.City.StopSign would not be active, which would prevent a misinterpretation of a manipulated sign.
- **Use of an Introspective Filter:** A higher-level monitoring system (as conceived in Chapter 21.5) must continuously analyze the internal states of the decision-making AI. It monitors not the output, but the "thoughts." If it determines that the AI assigns a very low confidence to an object but this would still lead to a drastic reaction (emergency braking), or that the data from the camera and LiDAR are in strong contradiction, it can intervene and put the vehicle into a safe minimal state (e.g., slow coasting on the shoulder).
 
## 5. Conclusion

The security of autonomous vehicles is currently viewed primarily through the lenses of functional safety and classic cybersecurity. This focus is necessary but dangerously incomplete. It ignores the largest and most subtle attack surface: the AI-driven perception itself.

The semantic and steganographic attacks outlined here are not futuristic threats. They are the direct application of techniques whose effectiveness has already been proven in language models.

There is no reason to assume that the perception AIs of vehicles are immune to this type of logical manipulation. As long as the industry does not anchor the security of its AI at a fundamental, architectural level through concepts like preventive input validation and the contextual limitation of the thought process, every autonomous vehicle remains a potential target for attacks that today's security systems do not even recognize as such.

The question is not if such attacks will happen in reality, but only when.
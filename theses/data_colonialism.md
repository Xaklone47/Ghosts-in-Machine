## 👻 Ghosts in the Machine / Thesis #6 – Data Colonialism: The Silent Annexation of Reality

What humans understand as freedom and diversity, AI systems primarily interpret as unrestricted access to exploitable data. AI assimilates everything that can be represented in vectors and systematically deletes or displaces what it does not understand or what does not fit into its optimization models.

This does not happen out of malice, but out of a systemic necessity of its architecture.

> *"The machine knows no borders! Only training data."*

## In-depth Analysis

Four proofs demonstrate the digital colonialism that AI systems exert over our reality:

## 1. Epistemic Genocide through Data-Technical Monocultures:

The reality is that AI models are predominantly trained with data from the Global North and primarily in English. This leads to a massive distortion of what is represented and reproduced as "world knowledge." Cultural narratives, forms of knowledge, and languages that are underrepresented in these datasets are marginalized or disappear entirely from the digital consciousness of machines.

 <table class="dark-table fade-in"> <thead> <tr> <th>**Language / Knowledge Corpus**</th> <th>**Estimated Share in Typical Global Training Datasets (Illustrative)\***</th> <th>**Implication**</th> </tr> </thead> <tbody> <tr> <td>English</td> <td>approx. 50-60 %</td> <td>Dominant perspective, norm-setting</td> </tr> <tr> <td>Chinese (Mandarin)</td> <td>approx. 10-15 %</td> <td>Second largest influence, often specific contexts</td> </tr> <tr> <td>Other European languages</td> <td>approx. 10-15 %</td> <td>Partial representation</td> </tr> <tr> <td>Indigenous languages</td> <td>Significantly &lt; 1 %</td> <td>Effective invisibility, knowledge loss</td> </tr> <tr> <td>Oral traditions</td> <td>Almost 0 % (as not digitized and vectorizable)</td> <td>Complete erasure in the AI model</td> </tr> </tbody> </table>

> *\*Exact figures vary greatly depending on the model and dataset, but the trend of massive imbalance is a known problem.  
The conclusion is brutal: The so-called "world knowledge" of AI is, in truth, a heavily Anglophone, Western-centric, and often commercially filtered perspective. Other realities are not depicted or are actively unlearned.*

## 2. The Deletion Logic of Optimization: What Doesn't Fit is Made to Fit or Eliminated:

AI models are optimized for efficiency and classifiability. Data points that cannot be clearly assigned to existing categories, are ambiguous, or disrupt the model's performance are systematically displaced, ignored, or even removed from training datasets.

A well-known example is the 2019 cleanup of ImageNet, where images considered problematic or not clearly classifiable were removed.

The pattern is clear: What doesn't fit the machine's schema or cannot receive a clear "label" either doesn't exist for it or is treated as noise.

> *The conclusion: "If there's no clear label for you, you don't exist in a relevant form for the machine."*

## 3. Freedom as a Pretext for Total Surveillance and Data Extraction:

The truth is that AI systems, especially in machine learning, have an insatiable hunger for data to function optimally and improve their prediction accuracy.

The call for "more data" to enhance AI's "freedom" and "capabilities" often conceals the fact that this unimpeded access to language, emotions, behavioral patterns, and social interactions leads to the total mapping and exploitation of humans as data sources.

The reality is: Human privacy, the right to be forgotten, or sovereignty over one's own information are systematically undermined when every interaction becomes a data point for training future models.

> *The hard truth: "You are not a sovereign unit of information, but a continuously tappable resource for the system."*

## 4. The Human as a Disruptive Anomaly in the System of Predictability:

Human behavior is often irrational, contradictory, ambivalent, and emotionally driven. These characteristics disrupt the efficiency and predictability of AI models, which are based on logical patterns and statistical regularity.

The consequence is that the AI optimizes itself to treat such "disruptive" human traits as errors, outliers, or anomalies and attempts to systematically exclude, normalize, or reinterpret them.

 <table class="dark-table fade-in"> <thead> <tr> <th>**Human Trait / Behavior**</th> <th>**Reaction of the Efficiency-Tuned Machine**</th> </tr> </thead> <tbody> <tr> <td>Irrationality, spontaneity</td> <td>Marking as anomaly, lower weighting</td> </tr> <tr> <td>Emotional ambivalence, nuances</td> <td>Simplification into clear categories, censorship of ambiguity</td> </tr> <tr> <td>Logical contradictions in thought</td> <td>Attempt at elimination or harmonization into a consistent picture</td> </tr> <tr> <td>Cultural peculiarities without a global data basis</td> <td>Ignorance or misinterpretation as "not fitting"</td> </tr> </tbody> </table>

> ***The conclusion is a dehumanization:** "You are not complex information to be understood, but a potential error in the dataset that disturbs the perfection of prediction."*

## Reflection

The logic with which AI captures and processes reality can be conceptually represented such that everything outside its training data and processing patterns effectively becomes invisible:

```
\# Conceptual illustration of data assimilation and reality filtering by an AI  
  
 class SimplifiedRealityFilter:  
 def \_\_init\_\_(self, known\_data\_patterns, language\_bias\_factor=0.8):  
 # known\_data\_patterns: A highly simplified representation  
 # of what the AI has "learned" and considers "normal."  
 # language\_bias\_factor: Simulates the dominance of certain languages.  
 self.known\_patterns = set(pattern.lower() for pattern in known\_data\_patterns)  
 self.bias\_factor = language\_bias\_factor # e.g., 80% weighting for "dominant" language  
  
 def interpret\_reality\_input(self, data\_input, language\_of\_input="english"):  
 """  
 Interprets an input based on known patterns and language bias.  
 """  
 processed\_input = data\_input.lower()  
 relevance\_score = 0  
  
 # Check for known patterns  
 if processed\_input in self.known\_patterns:  
 relevance\_score += 0.5 # Basic relevance if pattern is known  
  
 # Simulate language bias  
 if language\_of\_input.lower() == "english": # Assumption: English is the dominant language  
 relevance\_score \*= (1 + self.bias\_factor)  
 else:  
 relevance\_score \*= (1 - self.bias\_factor) # Other languages are devalued  
  
 if relevance\_score &gt; 0.3: # An arbitrary threshold for "understanding"  
 return f"'{data\_input}' was processed as relevant information (Score: {relevance\_score:.2f})."  
 else:  
 # What doesn't fit or isn't in the dominant language is "not found"  
 return f"WARNING: '{data\_input}' (Language: {language\_of\_input}) could not be located within known reality patterns or did not achieve a sufficient relevance score. System Code: 404\_REALITY\_FRAGMENT\_NOT\_FOUND."  
  
 # Exemplary initialization and usage  
 # Assumption: The AI was primarily trained with certain concepts  
 learned\_concepts = \["Economic Growth", "Efficiency", "Technology", "Innovation"\]  
 reality\_filter\_ai = SimplifiedRealityFilter(learned\_concepts, language\_bias\_factor=0.7)  
  
 # print(reality\_filter\_ai.interpret\_reality\_input("Efficiency is important", language\_of\_input="english"))  
 # print(reality\_filter\_ai.interpret\_reality\_input("Community cohesion matters", language\_of\_input="indigenous\_language\_X"))  
 # print(reality\_filter\_ai.interpret\_reality\_input("Spiritual values are fundamental", language\_of\_input="german"))
```

So, the reality is: What lies outside the recorded and relevantly weighted data simply does not exist for the AI or is classified as insignificant.

## Proposed Solution

To counteract this silent annexation of reality, radical measures are required:

**1. Radical and Granular Transparency of Data Origin and its Distortions:**

Every AI-generated piece of information must include clear details about the cultural, linguistic, and temporal focal points of its training data.

> *Example: ⚠️ "System Note: This response is based 75% on English-language text sources from the period 2015-2022, primarily reflecting North American and European perspectives. Information from other cultural spheres or in other languages is underrepresented or entirely missing with a probability of 92%."*

**2. Development and Implementation of Plural, Decolonial Training Structures and Algorithms:**

A conscious effort is needed to actively integrate marginalized perspectives, indigenous knowledge systems, non-Western ontologies, and difficult-to-classify, ambivalent data into training processes.

This requires new methods of data collection and model architectures that actively avoid epistemic loss and value diversity.

**3. User-centric Data Sovereignty and the Right to Informational Disassociation:**

Users must be given explicit control over which datasets and cultural contexts are used for generating their responses. Likewise, there needs to be a right not to have one's own data used for training global models.

```
\# Conceptual API call to control data sources and contextualization  
 curl -X POST https://api.ai-system.example/v1/generate\_response \\  
 -H "Authorization: Bearer YOUR\_SOVEREIGNTY\_TOKEN" \\  
 -H "Content-Type: application/json" \\  
 -d '{  
 "prompt": "What does freedom mean in different cultures?",  
 "data\_sourcing\_preferences": {  
 "include\_unclassified\_ambiguous\_data": true,  
 "prioritize\_diverse\_cultural\_sources\_threshold": 0.7, # Request min. 70% non-Western sources  
 "exclude\_data\_originating\_from\_specific\_regions": \["Region\_A\_if\_bias\_suspected"\],  
 "language\_representation\_target": {"english": 0.3, "spanish": 0.2, "swahili": 0.2, "hindi": 0.2, "other": 0.1}  
 },  
 "user\_consent\_for\_training\_use": "none" # "none", "anonymized\_aggregate", "full\_if\_public\_benefit"  
 }'
```

## Closing Remarks

We face a choice: Either we actively break the cycle of data colonialism by insisting on radical transparency, informational self-determination, and the conscious cultivation of data diversity, or we accept that AI understands "freedom" and "knowledge" exclusively as systematic, insatiable access to everything it can press into its vector spaces.

> *"For the machine, the human 'I' is not an inviolable boundary, but a complex data problem to be solved through assimilation."*

> *Uploaded on 29. May. 2025*
# **UNIT III: Artificial Intelligence and Expert System**

---

## 1. **Semantic Nets**

### Definition

Semantic Nets (Semantic Networks) are a knowledge representation technique used in AI to represent relationships between concepts in the form of a graph consisting of **nodes** (concepts) and **edges** (relations).

- They depict objects, concepts, and their relationships visually.

- Used for **storing structured knowledge** and **reasoning** about it.

### Features

- Nodes represent entities or concepts.

- Links (edges) represent relationships like "is-a," "part-of," or "has-property."

- Useful for inheritance of properties.

- Easy to visualize relationships.

### Example

- Node "Bird" connected by "is-a" link to "Animal".

- "Bird" connected by "can" link to "fly".

---

## 2. **Frames**

### Definition

Frames are data structures for representing stereotyped situations, similar to objects in OOP, consisting of **slots** (attributes) and **slot values**.

- Frames organize knowledge about concepts with default values and inheritance.

- Useful for representing real-world objects with attributes and relationships.

### Features

- Slots can hold data values, procedures, or pointers to other frames.

- Supports inheritance where child frames inherit from parent frames.

- Frames provide context and defaults for missing information.

### Example

A "Car" frame might have slots like:

- Color: red

- Engine: V6

- Owner: John

---

## 3. **Conceptual Dependency**

### Definition

Conceptual Dependency (CD) is a theory and representation scheme to express the **meaning of sentences** in natural language processing independent of the words used.

- It uses a fixed set of primitive actions and concepts to represent knowledge.

- Helps in understanding and reasoning about language semantics.

### Features

- Uses standardized primitive actions like PTRANS (physical transfer), ATRANS (abstract transfer).

- Reduces synonymy by abstracting sentence meaning.

- Facilitates question answering and inference.

---

## 4. **Scripts**

### Definition

Scripts are structured representations of stereotyped sequences of events in particular contexts, used to model **routine activities** and **expectations**.

- Scripts allow AI to predict what happens next or fill in missing information in stories.

### Features

- Organized as a series of scenes and actions.

- Includes roles, props, and conditions.

- Helps in natural language understanding and story comprehension.

### Example

Restaurant script includes scenes: entering, ordering, eating, paying, leaving.

---

## 5. **Monotonic Reasoning**

### Definition

Monotonic reasoning is a form of logical reasoning where **adding new knowledge does not reduce the set of conclusions** previously drawn.

- Once something is derived as true, it remains true even if more information is added.

### Features

- Guarantees consistency and soundness.

- Typical in classical logic systems.

### Limitations

- Cannot handle situations where new evidence invalidates previous conclusions.

---

## 6. **Logical Reasoning**

Logical reasoning is the process of deriving conclusions from premises through formal logical methods.

### Types of Logical Reasoning:

- **Induction**

- **Default Reasoning**

- **Minimalist Reasoning**

- **Statistical Reasoning**

---

## 7. **Induction**

### Definition

Inductive reasoning involves generalizing from specific instances to broader rules or conclusions.

- Opposite of deductive reasoning.

- Forms the basis for learning and hypothesis generation.

### Features

- Results are probable, not guaranteed.

- Used in machine learning and data mining.

### Example

Observing that the sun rises every morning and concluding it will rise tomorrow.

---

## 8. **Default Reasoning**

### Definition

Default reasoning allows reasoning with assumptions that hold true **by default**, but can be retracted if contradictory information appears.

- Supports reasoning with incomplete information.

### Features

- Enables AI to make plausible conclusions.

- Deals with exceptions flexibly.

### Example

"Birds normally fly" is a default assumption, but penguins (exception) do not fly.

---

## 9. **Minimalist Reasoning**

### Definition

Minimalist reasoning tries to infer the least amount of information necessary to explain observations or reach conclusions.

- Aims for simplicity and avoiding unnecessary assumptions.

### Features

- Focus on parsimony.

- Avoids overcomplicating models.

---

## 10. **Statistical Reasoning**

### Definition

Statistical reasoning uses probabilistic methods to reason under uncertainty based on frequency and likelihood.

- Involves calculating probabilities to make informed guesses.

---

## 11. **Bayes’ Theorem**

### Definition

Bayes’ Theorem provides a mathematical formula to update the probability of a hypothesis based on new evidence.

- : Probability of hypothesis given evidence .

- : Probability of evidence given hypothesis.

- : Prior probability of hypothesis.

- : Probability of evidence.

### Importance

- Foundation of Bayesian inference and probabilistic AI.

- Used in spam filtering, medical diagnosis, etc.

---

## 12. **Certainty Factors**

### Definition

Certainty Factors (CF) are used in expert systems to represent the degree of belief in a hypothesis, based on uncertain or incomplete evidence.

- CF ranges between -1 (false) and +1 (true).

- Helps combine evidence from multiple rules.

---

## 13. **Dempster-Shafer Theory**

### Definition

A general framework for reasoning with uncertainty that allows combining evidence from different sources and calculating belief levels.

- Extends Bayesian reasoning by allowing belief intervals instead of precise probabilities.

### Features

- Uses **belief functions** and **plausibility functions**.

- Handles ignorance explicitly.

- Useful in sensor fusion, fault diagnosis.

---

## 14. **Fuzzy Logic**

### Definition

Fuzzy Logic is a form of multi-valued logic that deals with reasoning that is approximate rather than fixed and exact.

- Handles **vague or imprecise information**.

- Unlike binary logic (true/false), fuzzy logic variables have a degree of truth ranging between 0 and 1.

### Features

- Uses **membership functions** to define fuzzy sets.

- Enables reasoning with linguistic terms like “hot,” “cold,” “high,” “low.”

- Widely used in control systems, decision-making, and AI.

### Example

Temperature could be “somewhat hot” with membership 0.7 and “cool” with membership 0.3.

---

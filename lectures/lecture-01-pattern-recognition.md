# Lecture 01 — What Is Pattern Recognition?

> **Purpose of these notes:** Help me remember the ideas clearly when I come back—not reproduce the lecture word for word. These notes reflect what I have worked through so far. They are not yet a claim that every slide has been covered.

## Where I am

**Status:** First guided pass through the main ideas done; remaining slide details and an exam-style check still need to be completed.

So far, the ideas make sense best when I ask:
- **Core task:** What is the model trying to do?
- **Learning paradigm:** What kind of feedback/data does it learn from?

That distinction cleared up a lot of my confusion.

---

## 1. The four core tasks

### Classification — predict a category

Examples:
- Email → Spam / Not Spam
- Weather → Sunny / Rainy / Cloudy
- Handwritten digit → one class from 0 to 9

The input can contain numbers. What matters is the **output**: a category or label.

### Regression — predict a numerical value

Examples:
- House → predicted price
- Student information → predicted exam score
- Weather data → predicted temperature

**My quick test:** If the question asks “which category?”, think classification. If it asks “what numerical value?”, think regression.

### Density estimation — describe how data is distributed

Example: I have the heights of 1,000 students and want to estimate which height ranges are common or rare.

This is not primarily about predicting one student's height or creating groups. It is about understanding the distribution of values.

### Clustering — discover groups in data

Example: A music app gets listening histories but no predefined user groups. It discovers groups of users with similar tastes.

The algorithm is not given the group labels in advance; it finds structure based on similarities in the data.

### The distinction I needed to slow down for

| Task | Question I should ask |
|---|---|
| Classification | Which label/category? |
| Regression | What numerical value? |
| Density estimation | Where is the data concentrated; what is common or rare? |
| Clustering | Which data points seem to belong together? |

**Density estimation vs. clustering:** density estimation describes the distribution of data; clustering discovers groups of data points. They can both help reveal structure, but they are not the same task.

---

## 2. Three learning paradigms

### Supervised learning — learn from examples with known answers

Example: Train on photos labeled **Cat** or **Dog**, then classify a new photo.

The labels provide target answers during training.

### Unsupervised learning — discover patterns without supplied target labels

Example: Give a music app listening histories without predefined user groups. It discovers groups of users with similar tastes.

### Reinforcement learning — learn from actions and their consequences

Example: A game-playing agent tries moves and receives rewards or penalties. Over time, it learns which actions tend to lead to better outcomes.

### The confusion I had: “Unsupervised and reinforcement both have no correct answer—so what's different?”

The useful distinction is the **kind of learning signal**:

- **Unsupervised:** find patterns in data.
- **Reinforcement:** choose actions and learn from reward feedback.
- **Supervised:** learn from labeled examples with known target answers.

Reinforcement learning does receive feedback: a reward signal. But a reward usually does not tell the agent the exact correct action for every situation.

### Core task vs. learning paradigm

These answer different questions:

- **Core task = what is being done?**
- **Learning paradigm = how is it being learned?**

Example: Predicting a house price from historical houses with known prices is **regression + supervised learning**.

Example: Discovering groups in unlabeled listening histories is **clustering + unsupervised learning**.

Don't treat the task names and paradigm names as competing choices; they describe different dimensions of a problem.

---

## 3. Types of classification

- **Binary:** choose between two classes. Example: Spam / Not Spam.
- **Multiclass:** choose one class from three or more. Example: Cat, Dog, or Bird.
- **Multilabel:** one input can receive multiple labels. Example: a photo labeled both **Dog** and **Person**.

My example was a photo containing both a dog and a person. The answer is **multilabel classification**, because both labels can apply to the same photo.

**Remember:** It is not just the number of objects that matters. The key is whether multiple labels are allowed for one input.

---

## 4. Density estimation: parametric vs. non-parametric

Imagine estimating the distribution of student heights.

### Parametric

Assume a distribution family first—for example, a Gaussian (normal) distribution—then estimate its parameters, such as the mean and variance.

**Mental model:** choose a distribution shape, then fit it to the data.

### Non-parametric

Do not require one fixed distribution family in advance; estimate the shape more flexibly from the observed data. **Kernel Density Estimation (KDE)** is an example.

**Mental model:** let the data inform the shape more flexibly.

“Non-parametric” does **not** mean that a method has no settings or assumptions at all.

**Still to practise:** I understand the intuition, but I should answer a quiz question distinguishing parametric from non-parametric before marking this fully secure.

---

## 5. Generalization — the idea that connected everything

A model should do well on examples it has **not** seen during training.

I understood this through the exam example: a student who memorizes practice answers but cannot solve a question with different wording has not learned the underlying pattern well.

Likewise, a model that performs well on training data but poorly on new data has **poor generalization**.

This leads to the idea of **overfitting**, which appears in Lecture 03.

---

## 6. Quick self-check

Try to answer these without looking above.

1. A model predicts whether an email is spam. What is the core task?
2. A model predicts a house's price. What is the core task?
3. An algorithm discovers customer groups without predefined labels. What are the core task and learning paradigm?
4. A game-playing agent learns from rewards after taking actions. Which learning paradigm?
5. A photo gets both the labels **Dog** and **Person**. What type of classification?
6. A model assumes a Gaussian distribution and estimates its mean and variance. Parametric or non-parametric?
7. A model performs well on training data but poorly on new data. What is the problem?

<details>
<summary>Answers — open after trying</summary>

1. Classification.
2. Regression.
3. Clustering + unsupervised learning.
4. Reinforcement learning.
5. Multilabel classification.
6. Parametric density estimation.
7. Poor generalization; likely overfitting.

</details>

---

## 7. What is covered, and what comes next?

**Covered in our guided first pass**
- The four core tasks: classification, regression, density estimation, clustering.
- Supervised, unsupervised, and reinforcement learning.
- Core task vs. learning paradigm.
- Binary, multiclass, and multilabel classification.
- Parametric vs. non-parametric density estimation (introductory intuition).
- Generalization at an introductory level.

**Still to verify against the full Lecture 01 slide sequence**
- Any other slide-specific types, workflow diagrams, algorithm lists, or terminology not yet discussed.
- The parametric/non-parametric quiz check.
- A short mixed exam-style review before calling Lecture 01 complete.

**Next:** Continue from the remaining Lecture 01 slide topics. Keep the notes short and add to them only when a concept has actually been taught or clarified.

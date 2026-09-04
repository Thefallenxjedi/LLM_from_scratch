# Lecture 3: Pretraining LLMs vs Finetuning LLMs

**Video Link:** [YouTube Link](https://www.youtube.com/watch?v=-bsa3fCNGg4)

---

# 1. What is this lecture about?

This lecture breaks down the two massive foundational stages required to build a Large Language Model (LLM) from scratch: Pre-training and Fine-tuning. It explains how models initially gain their broad intelligence by reading the internet, and how companies subsequently adapt those generic models to perform highly specialized tasks in fields like law, telecom, and banking. Understanding these two phases is essential because it demystifies how AI systems are actually trained in the real world and why companies spend millions of dollars on data engineering.

# 2. Core Idea

**If you remember only one thing from this lecture, remember this:**
Building a powerful LLM requires two main steps: first, you "pre-train" a model on a massive amount of generic internet data so it understands human language, and second, you "fine-tune" it on a smaller, specific set of data so it becomes an expert at a specific job.

# 3. Key Concepts

*   **Pre-training (Creating the Foundational Model)**
    *   *Simple explanation:* Feeding a neural network billions of words from the internet and asking it to constantly play a game of "guess the next word" (auto-regression).
    *   *Why it matters:* This gives the AI its broad knowledge base and fundamental grasp of grammar, logic, and facts. The result of this stage is called a **Foundational Model** or **Base Model**.
*   **Fine-tuning (Specialization)**
    *   *Simple explanation:* Taking a pre-trained model and training it a little bit more, but this time on highly specific, curated data (like legal cases or customer support logs).
    *   *Why it matters:* A foundational model gives generic answers. Fine-tuning ensures the AI speaks your company's language, obeys specific instructions, and understands niche industry knowledge.
*   **Raw / Unlabeled Data**
    *   *Simple explanation:* Data that is just plain text scraped from the internet, with no specific tags or categories. This is used entirely for pre-training.
*   **Labeled Data**
    *   *Simple explanation:* Data that has clear instructions and expected answers (e.g., 5,000 emails explicitly marked as "Spam" or "Not Spam"). This is used for fine-tuning.

# 4. Build Your Intuition

**Think of it like getting an education:**
*   **Pre-training** is like sending a child to K-12 school and college to get a broad, general education. They read thousands of books, learn history, math, and how to write beautifully. At the end, they are highly capable but generic (a Foundational Model).
*   **Fine-tuning** is like that same person going to Medical School or Law School. They use their broad grasp of the world to learn a highly specific skill set. You wouldn't hire a general college grad to defend you in court; you would hire the one who was *fine-tuned* on legal data.

# 5. How It Works

**Step 1: Collect Massive Raw Data → Step 2: Pre-train the Foundational Model → Step 3: Fine-tune on Specialized Data**

*   **Step 1: Collect Data:** Gather billions of words from websites (Common Crawl), Wikipedia, and digitized books.
*   **Step 2: Pre-train (Auto-regression):** The model looks at a sentence ("The lion is in the...") and tries to predict the next word. It does this billions of times on unlabeled data until it becomes a powerful, general-purpose "Foundational Model."
*   **Step 3: Fine-tune:** A company feeds the Foundational Model a smaller set of *labeled* data (like instruction-answer pairs) to specialize the model for tasks like translation, classification, or specialized customer service.

# 6. Practical / Real-World Applications

*   **Telecommunications:** SK Telecom fine-tuned GPT-4 specifically on Korean telecom conversations, increasing their AI's intent recognition accuracy by 33%.
*   **Law / Attorneys:** *Harvey* is an AI platform that took a foundational model and fine-tuned it exclusively on legal case histories so it can reliably assist top global law firms.
*   **Banking:** JP Morgan Chase built its own fine-tuned LLM for internal employees using proprietary financial data that a public model like ChatGPT wouldn't have access to.

# 7. Practical Example

Imagine you are the CEO of an airline. You want a chatbot on your website.
*   If you use a **Pre-trained Foundational Model** out of the box, and a user asks, "What's the cancellation policy for flight 102?", the AI might give a generic answer about standard aviation rules based on Wikipedia.
*   If you **Fine-tune** that model on your airline's specific, internal database of flight policies and customer service logs, it will perfectly answer the user based on your exact corporate rules.

# 8. Python / Coding Practice

**No coding exercise is necessary for this lecture.**

# 9. Important Technical Details

*   **Cost of Pre-training:** Pre-training is astronomically expensive due to the massive GPU compute required. Training GPT-3 cost approximately **$4.6 million**. This is why normal people do not pre-train LLMs; they start with existing foundational models and just fine-tune them.
*   **The Datasets:** GPT-3 was trained on ~300 billion tokens (words). 
    *   **Common Crawl:** A public database of scraped internet websites (made up 60% of GPT-3's data, or 410 billion words).
    *   **WebText2:** High-quality links from Reddit.
    *   **Books & Wikipedia:** Comprised billions of additional words for factual knowledge.
*   **Auto-regression:** The technical term for training an AI by hiding the next word in a sequence and forcing it to guess what comes next.

# 10. Common Confusions

**Confusion:** Why is it called "pre"-training instead of just "training"? 
**Correct understanding:** It is called "pre"-training simply because the "fine-tuning" phase comes afterward. Pre-training is the foundational training phase that prepares the model for specific fine-tuning later.

**Confusion:** Pre-trained models can only do word completion.
**Correct understanding:** Surprisingly, when a model is trained *only* to predict the next word on a massive scale, it naturally develops the ability to do translation, summarization, and multiple-choice questions without ever being explicitly programmed to do so!

# 11. What You Should Be Able to Explain After This Lecture

*   [ ] I can explain the difference between Pre-training and Fine-tuning.
*   [ ] I can explain what a "Foundational Model" is.
*   [ ] I can name two sources of data used to pre-train large language models.
*   [ ] I can explain why big corporations spend money to fine-tune models instead of just using ChatGPT out of the box.

# 12. Active Recall Questions

1. What is the fundamental difference in the *type of data* used in Pre-training versus Fine-tuning?
2. What does the term "auto-regression" mean in the context of training an LLM?
3. Why did a platform like *Harvey* (the legal AI) need to be fine-tuned? Why wasn't GPT-4 good enough on its own?
4. What is "Common Crawl" and why is it important to AI?
5. Why is pre-training almost exclusively done by giant tech companies rather than individual developers?

# 13. Concept-Building Exercises

**Level 1: Understand**
Explain the difference between a foundational model and a fine-tuned model using an analogy other than the "school/college" one provided above.

**Level 2: Apply**
For each of the following scenarios, determine if the company needs to heavily **Pre-train** a new model from scratch, or simply **Fine-tune** an existing foundational model:
1. A hospital wants an AI that strictly answers questions based on their internal, highly confidential patient care manuals.
2. A tech giant wants to release a brand new open-source AI rivaling GPT-4 to the public.
3. A startup wants an AI that sorts their daily inbound emails into "Urgent", "Sales", and "Spam".

**Level 3: Think**
The lecture notes that an LLM trained *only* on the simple task of predicting the next word (auto-regression) suddenly becomes capable of translating languages and passing exams. Why do you think a "guess the next word" game leads to such advanced reasoning skills when scaled up to billions of words?

### Exercise Solutions

*   **Level 1 Solution:** (Example) A foundational model is like a blank smartphone loaded with a basic operating system. It works and is generally smart. Fine-tuning is like downloading specific apps (a banking app, a fitness app) that make the phone incredibly useful for highly specific jobs. *(Reinforces: General vs Specific capability).*
*   **Level 2 Solution:** 1. Fine-tune (They just need to teach a smart model their specific internal data). 2. Pre-train (They need to build a new foundational model from the ground up on billions of tokens). 3. Fine-tune (This is a classic classification task that requires a labeled dataset of their specific emails). *(Reinforces: Practical application of the two stages).*
*   **Level 3 Solution:** To accurately predict the next word in a complex sentence (e.g., a sentence about quantum physics, or a sentence half in English and half in French), the AI is mathematically forced to learn the underlying rules of grammar, facts, context, and logic. At a massive scale, "guessing the word" requires an internal model of how the world actually works. *(Reinforces: The emergent properties of pre-training).*

# 14. Practice Tasks

**Task 1: Understand**
Do a quick Google search for "Common Crawl". Look at their website to understand just how massive this open-source data repository is. Realize that almost every major AI you use today has "read" this database.

**Task 2: Apply**
Think of a hobby or niche industry you are involved in. Write down exactly what kind of "labeled data" you would need to collect to fine-tune a model to be an expert in your niche.

# 15. One-Page Revision

**Core idea:** Building an LLM requires Pre-training (giving the AI a broad, general education via massive internet data) followed by Fine-tuning (giving the AI specific instructions or proprietary data to make it a domain expert).
**Key concepts:** 
*   **Foundational Model:** The general-purpose AI created after pre-training.
*   **Labeled vs Unlabeled Data:** Pre-training uses massive, unlabeled raw text. Fine-tuning uses smaller, neatly labeled examples.
*   **Cost:** Pre-training costs millions of dollars in compute; fine-tuning is much cheaper and accessible.
**Remember:** Even though pre-training just teaches the AI to guess the next word (auto-regression), this process inherently teaches the AI grammar, translation, and logic.
**Most important relationship:** Pre-training provides the raw intelligence; Fine-tuning provides the specific utility. 

# 16. Connection to the Bigger Picture

*   **What should the learner already know?** The basic terminology of AI vs ML vs DL vs LLMs from Lecture 2.
*   **What does this lecture prepare them for?** It gives the high-level roadmap of how an LLM is actually built in the real world before diving into the specific math and code.
*   **What is likely to come next?** The next lectures will start diving deeply into the technical architecture that allows pre-training to happen: the Transformer, positional encoding, and self-attention mechanisms.

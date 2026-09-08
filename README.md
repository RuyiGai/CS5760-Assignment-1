# CS5760 Natural Language Processing - Homework 1

## Student Information

- **Name:** Ruyi Gai
- **Student ID:** 700778329
- **Course:** CS5760 Natural Language Processing
- **Semester:** Fall 2026
- **University:** University of Central Missouri

---
## Files

```text
Homework 1.docx
Homework 1.ipynb
README.md```

- `Homework 1.ipynb` — Contains the Python programming code, execution results, and written explanations.
- `Homework 1.docx` — Contains screenshots of the short-answer and programming questions.
- `README.md` — Provides an overview of the assignment and summarizes the completed work.

---

## Assignment Overview

This homework covers several fundamental Natural Language Processing (NLP) concepts, including Regular Expressions, Byte Pair Encoding (BPE), Bayes' Rule, Add-1 Smoothing, Tokenization, and Multiword Expressions (MWEs).

The assignment includes both theoretical questions and programming tasks. The programming work was implemented in Python, and the completed work is provided in the Jupyter Notebook and Word document.

---

## Q1: Regular Expressions

This section focuses on writing regular expressions for different text-matching tasks.

The tasks include:

1. Matching U.S. ZIP codes.
2. Finding words that do not start with a capital letter.
3. Extracting numbers with optional signs, commas, decimals, and scientific notation.
4. Matching different spellings of "email".
5. Matching variations of the word "go" with optional punctuation.
6. Matching lines that end with a question mark and optional closing quotes or brackets.

These exercises demonstrate the use of word boundaries, disjunction, optionality, repetition, character classes, and anchors in regular expressions.

---

## Q2: Byte Pair Encoding (BPE)

### Q2.1: Manual BPE on a Toy Corpus

The first part applies BPE manually to the toy corpus provided in the assignment.

The work includes:

- Adding the end-of-word marker `_`.
- Creating the initial vocabulary.
- Computing bigram frequencies.
- Performing the first three BPE merges.
- Updating the corpus after each merge.
- Showing the new tokens and vocabulary after each step.

### Q2.2: Mini-BPE Learner

A Python implementation of a mini-BPE learner was developed.

The program:

- Prepares the corpus using character-level tokens and the `_` end-of-word marker.
- Counts adjacent symbol pairs.
- Repeatedly merges the most frequent pair.
- Tracks the vocabulary size after each merge.
- Builds a BPE segmenter using the learned merge ranks.
- Segments words such as `new`, `newer`, `lowest`, `widest`, and an invented word.

The reflection explains how subword tokenization helps reduce the Out-of-Vocabulary (OOV) problem and how learned subwords can correspond to meaningful morphemes.

### Q2.3: Chinese BPE

This section trains BPE on a Chinese paragraph and uses Python to implement the BPE training, merging, and segmentation processes.

The experiment includes:

- Adding the `_` end-of-word marker.
- Learning 30 BPE merges.
- Identifying the five most frequent merges.
- Finding the five longest learned subword tokens.
- Segmenting selected Chinese words.
- Analyzing the types of Chinese subwords learned.
- Discussing the advantages and disadvantages of BPE for Chinese.

The results demonstrate that BPE can learn frequent Chinese character combinations as well as longer subword or word-level units.

---

## Q3: Bayes' Rule Applied to Text

This section explains the basic terms used in Bayes' Rule for text classification:

- **\(P(c)\):** Prior probability of a class.
- **\(P(d|c)\):** Probability of a document given a class.
- **\(P(c|d)\):** Probability of a class given a document.

The section also explains why the denominator \(P(d)\) can be ignored when comparing different classes because it is the same for all classes being compared.

---

## Q4: Add-1 Smoothing

This section applies Add-1 (Laplace) smoothing to a text classification example.

The calculations include:

- Computing the denominator for likelihood estimation.
- Calculating \(P(\text{predictable}|-)\).
- Calculating \(P(\text{fun}|-)\) when the word does not appear in the negative documents.

The example demonstrates how Add-1 smoothing prevents unseen words from receiving a probability of zero.

---

## Q5: Tokenization

### Q5.1: Tokenize a Chinese Paragraph

A Chinese paragraph was tokenized using two approaches:

1. Naïve space-based tokenization.
2. Manual tokenization.

Because Chinese text normally does not use spaces between words, naïve space-based tokenization treats the paragraph as one large token. The manual version separates Chinese characters and punctuation marks.

The differences between the two tokenization approaches are also discussed.

### Q5.2: Compare with an NLP Tool

The Chinese paragraph was also tokenized using the open-source `jieba` tokenizer.

The manual character-level tokenization was compared with `jieba`'s word-level tokenization.

For example:

- `喜 + 欢` → `喜欢`
- `学 + 习` → `学习`

The differences occur because the two approaches use different tokenization granularities.

### Q5.3: Multiword Expressions (MWEs)

Three Chinese multiword expressions were identified:

- **北京** — a place name.
- **心想事成** — a Chinese idiom.
- **自然语言处理** — a fixed technical term in computer science.

These expressions can be treated as single tokens because their combined meanings are more specific than the meanings of their individual parts.

### Q5.4: Reflection

The reflection discusses:

- The difficulty of identifying Chinese word boundaries.
- Differences between Chinese and English tokenization.
- The effect of punctuation.
- Differences in morphology.
- The challenges created by Multiword Expressions (MWEs).

---

## Technologies Used

- **Python**
- **Jupyter Notebook**
- **Regular Expressions (Regex)**
- **jieba**
- **Byte Pair Encoding (BPE)**
- **Natural Language Processing (NLP)**

---

## Conclusion

This homework provided practical experience with several fundamental NLP techniques. The exercises covered regular expressions, subword tokenization using BPE, Bayes' Rule, Add-1 smoothing, Chinese tokenization, and Multiword Expressions.

The programming tasks demonstrated how different tokenization strategies affect the representation of text, especially for Chinese, where word boundaries are not explicitly marked by spaces. Overall, the assignment helped strengthen both the theoretical understanding and practical implementation of basic NLP methods.

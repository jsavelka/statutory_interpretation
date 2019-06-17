# Statutory Interpretation Data Set

This repository contains the data set created for the following research paper
presented at the International conference on Artificial Intelligence and Law
(ICAIL) 2019 in Montreal:

Jaromir Savelka, Huihui Xu, and Kevin D. Ashley. 2019. Improving Sentence
Retrieval from Case Law for Statutory Interpretation. In *Seventeenth
International Conference on Artificial Intelligence and Law (ICAIL ’19), June
17–21, 2019, Montreal, QC, Canada*, Floris Bex (Ed.). ACM, New York, NY, USA, 10
pages. https://doi.org/10.1145/3322640.3326736

## Task
Given a statutory provision, user's interest in the meaning of a phrase from the
provision, and a list of sentences  we would like to rank more highly the
sentences that elaborate upon the meaning of the statutory phrase of interest,
such as:

* **definitional sentences** (e.g., a sentence that provides a test for when the phrase applies)
* sentences that **state explicitly in a different way** what the statutory phrase means or state what it does not mean
* sentences that provide an **example**, instance, or counterexample of the phrase
* sentences that show **how a court determines** whether something is such an
example, instance, or counterexample.

## Corpus Overview
For this corpus we selected three terms from different provisions of the United
States Code:

* "independent economic value" (18 U.S. Code § 1839(3)(B))
* "identifying particular" (5 U.S. Code § 552a(a)(4))
* "common business purpose" (29 U.S. Code § 203(r)(1))

For each term we have collected a set of sentences by extracting all the
sentences mentioning the term from the court decisions retrieved from the
[Caselaw access project](https://case.law) data.

In total the corpus consists of 4,635 sentences.

The sentences are classified into four categories according to their usefulness
for the interpretation:

* **high value** - sentence intended to define or elaborate on the meaning of
the term
* **certain value** - sentence that provides grounds to elaborate on the term's
meaning
* **potential value** - sentence that provides additional information beyond
what is known from the provision the term comes from
* **no value** - no additional information over what is known from the provision

See [Annotation guidelines](https://github.com/jsavelka/statutory_interpretation/annotation_guidelines.pdf)
for additional details.

## Data Structure
Each zip file contains data related to one of the three queries. There are four
files in total containing the texts of different granularity. These allow to
replicate experiments reported in the paper cited above.

* case
    * original_id - case id from Caselaw access project
    * name
    * short_name
    * date
    * official_date
    * official citation
    * alternate_citations
    * court
    * short_court - court abbreviation
    * jurisdiction
    * short_jurisdiction - jurisdiction abbreviation
    * attorneys
    * parties
    * judges
    * text
* opinion
    * case_id - pointer to the case the opinion belongs to
    * author
    * type - e.g., concurrence, dissent
    * position - position of the opinion within the case
    * text
* paragraph
    * case_id - pointer to the case the opinion belongs to
    * opinion_id - pointer to the opinion the paragraph belongs to
    * position - position of the paragraph within the opinion
    * text
* sentence
    * case_id - pointer to the case the sentence belongs to
    * opinion_id - pointer to the opinion the sentence belongs to
    * paragraph_id - pointer to the paragraph the sentence belongs to
    * position - position of the sentence within the paragraph
    * text

## Terms of Use
For use of the data we kindly ask you to provide the two following attributions:

Jaromir Savelka, Huihui Xu, and Kevin D. Ashley. 2019. Improving Sentence
Retrieval from Case Law for Statutory Interpretation. In *Seventeenth
International Conference on Artificial Intelligence and Law (ICAIL ’19), June
17–21, 2019, Montreal, QC, Canada*, Floris Bex (Ed.). ACM, New York, NY, USA, 10
pages. https://doi.org/10.1145/3322640.3326736

The President and Fellows of Harvard University, Caselaw access project,
[Caselaw access project](https://case.law), 2018.
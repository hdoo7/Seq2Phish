# Seq2Phish Dataset

This repository provides the dataset used in the paper **Seq2Phish**, a sequence-to-sequence learning framework for proactive phishing-domain defense.

Seq2Phish models phishing-domain generation as a character-level domain-transformation task. Given a legitimate domain, the model learns patterns used by attackers to create impersonated domains, such as character insertion, deletion, substitution, hyphen insertion, number insertion, top-level domain changes, and more complex alterations.

## Dataset Overview

The dataset contains paired examples of legitimate domains and their corresponding impersonated phishing domains.

- **Total rows:** 5,680 domain pairs
- **Columns:** `original_domain`, `impersonated_domain`
- **Unique legitimate domains:** 4,467
- **Unique impersonated domains:** 5,358
- **Longest legitimate domain:** 37 characters
- **Longest impersonated domain:** 67 characters
- **Average legitimate-domain length:** 14.10 characters
- **Average impersonated-domain length:** 15.92 characters

## Dataset Format

Each row represents a legitimate-to-impersonated domain transformation that can be used to study phishing-domain generation and detection.

Example format:

| Column | Description |
|---|---|
| `legitimate` | The original legitimate domain |
| `impersonated` | The phishing or lookalike domain |
| `similarity` | Character-level similarity between the legitimate and impersonated domains |
| `technique` | The domain-manipulation category |

Example:

```csv
legitimate,impersonated,similarity,technique
netify.ai,blogspot.co.nz,0.1739,complex_alteration
xyz-racing.com,xyz-racing.co,0.9630,changed_tld
apsystems.com,agpsystems.com,0.9630,added_characters

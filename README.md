# PROPHET Dataset

This repository provides the phishing-domain dataset introduced in the paper:

**PROPHET: Proactive Phishing-Domain Generation via Transformation**

PROPHET is the first sequence-to-sequence framework that reformulates phishing-domain defense as a domain-transformation learning problem. Instead of classifying previously observed domains as benign or malicious, PROPHET learns character-level transformations between legitimate domains and their impersonated phishing variants and generates plausible phishing-domain candidates before attackers deploy them.

To support this research, we curated and publicly release a paired dataset of legitimate and impersonated domains for reproducible phishing-domain generation and detection research.

---

## Dataset Overview

The dataset contains paired examples of legitimate domains and their corresponding impersonated phishing domains.

### Statistics

| Metric                             | Value                                  |
| ---------------------------------- | -------------------------------------- |
| Total domain pairs                 | 5,680                                  |
| Unique legitimate domains          | 4,467                                  |
| Dataset format                     | Paired legitimate–impersonated domains |
| Longest legitimate domain          | 37 characters                          |
| Longest impersonated domain        | 67 characters                          |
| Average legitimate-domain length   | 14.10 characters                       |
| Average impersonated-domain length | 15.92 characters                       |
| Similarity range                   | 14.49% – 98.41%                        |

The dataset was semi-manually collected and curated using phishing URLs from multiple public sources, including:

* Kaggle phishing datasets
* OpenPhish
* Public phishing-domain repositories on GitHub

---

## Dataset Format

Each row represents a transformation from a legitimate domain to an impersonated phishing domain.

| Column         | Description                                                                      |
| -------------- | -------------------------------------------------------------------------------- |
| `legitimate`   | Original legitimate domain                                                       |
| `impersonated` | Corresponding phishing or impersonated domain                                    |
| `similarity`   | Character-level similarity score between the legitimate and impersonated domains |
| `technique`    | Phishing-domain manipulation category                                            |

Example:

```csv
legitimate,impersonated,similarity,technique
netify.ai,blogspot.co.nz,0.1739,complex_alteration
xyz-racing.com,xyz-racing.co,0.9630,changed_tld
apsystems.com,agpsystems.com,0.9630,added_characters
```

---

## Phishing-Domain Manipulation Categories

The dataset labels each domain pair according to the primary manipulation technique used by the impersonated domain.

| Technique                | Description                                                                                      |
| ------------------------ | ------------------------------------------------------------------------------------------------ |
| `complex_alteration`     | Combination of multiple modifications (e.g., substitution + TLD change, insertion + hyphenation) |
| `changed_tld`            | Modification of the top-level domain                                                             |
| `added_characters`       | One or more characters inserted into the original domain                                         |
| `removed_characters`     | One or more characters removed from the original domain                                          |
| `character_substitution` | Characters replaced with visually or structurally similar alternatives                           |
| `hyphen_insertion`       | Hyphens inserted into the domain name                                                            |
| `number_insertion`       | Numeric characters inserted into the domain name                                                 |

### Category Distribution

| Technique              | Percentage |
| ---------------------- | ---------: |
| Complex Alteration     |     65.23% |
| Changed TLD            |     11.23% |
| Added Characters       |     10.72% |
| Removed Characters     |      7.32% |
| Character Substitution |      3.43% |
| Hyphen Insertion       |      1.64% |
| Number Insertion       |      0.42% |

The dominance of complex alterations highlights that attackers frequently combine multiple transformation strategies rather than relying on a single modification.

---

## Research Applications

This dataset can support research in:

* Phishing-domain generation
* Typosquatting analysis
* Brand impersonation detection
* Domain similarity modeling
* Sequence-to-sequence learning
* Character-level transformation learning
* Proactive phishing-domain defense
* DNS filtering and threat intelligence
* Cybersecurity machine learning

---

## License

Please refer to the repository license for usage and redistribution terms.

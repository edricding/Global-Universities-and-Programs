# University & Program Dataset (AU / CN / HK / SG / UK)

A public dataset of major universities and their programs across four Commonwealth regions (Australia, United Kingdom, Hong Kong, Singapore), plus comprehensive coverage of universities in China. Programs are linked to universities via `university_id`.

## Overview

This repository contains:

* **Universities dataset** for:

  * Australia (AU)
  * China (CN)
  * Hong Kong (HK)
  * Singapore (SG)
  * United Kingdom (UK)
* **Programs dataset** for **Australia / Hong Kong / Singapore / United Kingdom**, covering:

  * **Bachelor**
  * **Master**
  * **PhD**
* A **China University Major Naming Standard** document to support standardized major naming for Chinese universities.

> Note: Program coverage outside China includes Bachelor/Master/PhD where available. Some integrated degrees (e.g., Master–PhD tracks) are recorded using the **minimum entry level** (see “Degree Level Rules”).

## Data Source & Credits

* **Date:** 2026.01
* **Sources:** Public information collected from online resources (official university websites and other publicly accessible web pages).
* **Collector:** Edric
* **License / Usage:** Provided for **public use**. 

## ID Ranges (Mapping by `university_id`)

The `university_id` field is used as the primary key to connect universities and their programs.

| `university_id` Range | Region              |
| --------------------- | ------------------- |
| 1 – 45                | Australia (AU)      |
| 46 – 2676             | China (CN)          |
| 2677 – 2686           | Hong Kong (HK)      |
| 2687 – 2698           | Singapore (SG)      |
| 2699 – 2719           | United Kingdom (UK) |

## Relationship Model

Programs reference universities by `university_id`.
Typical linkage pattern:

* `universities` table/file: `university_id` (PK)
* `programs` table/file: `university_id` (FK)

This enables you to join/merge datasets and retrieve all programs offered by a given university.

## Degree Level Rules

For **non-China universities (AU/HK/SG/UK)**, programs generally include **Bachelor**, **Master**, and **PhD** levels.

Some programs are integrated tracks (e.g., Bachelor–Master, Master–PhD, or combined research pathways). In such cases, the program is labeled with the **minimum degree level**:

* Bachelor–Master integrated → labeled as **Bachelor**
* Master–PhD integrated → labeled as **Master**

This convention ensures consistent filtering and downstream processing.

## China Coverage

* Includes **the vast majority of Chinese universities** (broad coverage).
* A separate document is included for **Chinese university major naming standards** to support normalization and consistent taxonomy across datasets.

## Files

Commonly included components in this repository may include (names depend on your repo structure):

* `universities.*` — university list with `university_id`
* `programs.*` — program list linked by `university_id`
* `china-major-naming-standard.*` — Chinese major naming standard / normalization guideline

## Recommended Use Cases

* University/program search and filtering
* Study abroad consulting workflows
* Dataset-driven matching / recommendation systems
* Analytics on program offerings by region and level
* Data normalization and taxonomy alignment for Chinese majors

## Disclaimer

This dataset is compiled from publicly available online sources and may contain omissions, outdated entries, or inconsistencies due to changes on university websites or source pages.
If you identify issues or want to contribute corrections, please open an issue or submit a pull request.

@Edric 2026.01

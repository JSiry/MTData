# MTData

MTData is a cross-subject dataset for cognitive diagnosis, collected from offline standardized mathematics and physics tests in China. It contains **3,242,146 response records from the same 39,062 students**, covering **832 classes, 102 schools, 65 districts, and 15 cities**.

The dataset accompanies [A Cross-subject Enhancement Model and Dataset for Cognitive Diagnosis](https://doi.org/10.1109/TCE.2026.3722386), which introduces CECD-II for cross-subject cognitive diagnosis.

## Features

- Aligned mathematics and physics records from the same students.
- Standardized assessments of students learning both subjects concurrently.
- Four-level group attributes: class, school, district, and city.
- Exercise-level knowledge concept and ability labels.
- Anonymized student and group identifiers.

## Statistics

| Subject | Students | Exercises | Knowledge concepts | Abilities | Response records |
| --- | ---: | ---: | ---: | ---: | ---: |
| Mathematics | 39,062 | 57 | 54 | 6 | 2,226,534 |
| Physics | 39,062 | 26 | 25 | 5 | 1,015,612 |

**Correction:** Physics has 25 knowledge concepts; 26 in the paper is a typo.

This release contains the full dataset; the paper's MTData experiments use a 5,000-student subset.

## Files

Download and extract [MTData.zip](./MTData.zip):

```text
MTData/
├── MTData_Math.csv
└── MTData_Physics.csv
```

Both files are UTF-8 with BOM, with English headers and Chinese concept and ability labels.

## Fields

Each row records one student's response to one exercise.

| Field | Description |
| --- | --- |
| `student_id` | Anonymized student ID, shared across subjects. |
| `exercise_id` | Subject-specific exercise ID. |
| `response` | Obtained score, including partial credit. |
| `question_type` | `objective` or `subjective`. |
| `knowledge_concepts` | Comma-separated knowledge concept labels. |
| `abilities` | Comma-separated ability labels. |
| `max_score` | Maximum exercise score. |
| `test_time` | Assessment occasion: `T1` or `T2`. |
| `city_code` | Anonymized city code. |
| `district_code` | Anonymized district code. |
| `school_code` | Anonymized school code. |
| `class_code` | Class code within its parent groups. |

## Citation

```bibtex
@article{guan2026mtdata,
  author  = {Guan, Zheng and Liu, Jie and Wang, Xue and Yang, Zhijun and Qian, Wenhua},
  title   = {A Cross-subject Enhancement Model and Dataset for Cognitive Diagnosis},
  journal = {IEEE Transactions on Consumer Electronics},
  year    = {2026},
  doi     = {10.1109/TCE.2026.3722386}
}
```


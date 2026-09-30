# Day 14 — Reflection

## Evaluation Report & Failure Analysis

Dùng kết quả thật trong `artifacts/benchmark_results.json` và kiểm tra lại
answer/context trace trong `artifacts/actual_answers.json` trước khi kết luận.

---

## 1. Benchmark Results Summary

**Overall pass rate:** ____%

| Metric | Average | Min | Max | Nhận xét |
|---|---:|---:|---:|---|
| Context Recall | | | | |
| Context Precision | | | | |
| Faithfulness | | | | |
| Relevance | | | | |
| Completeness | | | | |
| Overall Score | | | | |

**Score interpretation**

- Metrics/cases ở mức Good (0.8–1.0): ____
- Metrics/cases ở mức Needs Work (0.6–0.8): ____
- Metrics/cases ở mức Significant Issues (<0.6): ____

**Failure type distribution**

| Failure Type | Count | Percentage |
|---|---:|---:|
| hallucination | | |
| irrelevant | | |
| incomplete | | |
| off_topic | | |
| refusal | | |

**Chẩn đoán tổng quan:** Vấn đề chính nằm ở retrieval, generation hay cả hai?
Dùng ít nhất hai metrics để bảo vệ kết luận.

> *Câu trả lời:*

---

## 2. Top 3 Worst Failures — 5 Whys

Phân loại failure trước khi đề xuất fix. Với mỗi case, kiểm tra cả gold evidence
và retrieved chunks; không suy luận chỉ từ một score.

### Failure 1

**ID và question:**

> *Điền:*

**Expected answer:**

> *Điền:*

**Actual answer:**

> *Điền:*

**Scores:** Context Recall: ____ | Context Precision: ____ | Faithfulness: ____ |
Relevance: ____ | Completeness: ____ | Overall: ____

**Evidence inspection:** Retriever lấy đúng/thiếu/thừa chunks nào?

> *Câu trả lời:*

| Level | Question | Answer |
|---|---|---|
| Symptom | Vấn đề quan sát được là gì? | |
| Why 1 | Tại sao symptom xảy ra? | |
| Why 2 | Tại sao nguyên nhân trên xảy ra? | |
| Why 3 | Tại sao vấn đề đó chưa được ngăn chặn? | |
| Why 4 | Tại sao cơ chế hiện tại chưa phát hiện hoặc xử lý được? | |
| Why 5 | Root cause có thể hành động được là gì? | |

**Root cause từ `find_root_cause()`:**

> *Paste output:*

**Bạn đồng ý hay không? Dẫn evidence từ trace:**

> *Câu trả lời:*

**Proposed fix cụ thể:**

> *Câu trả lời:*

### Failure 2

**ID và question:**

> *Điền:*

**Expected answer:**

> *Điền:*

**Actual answer:**

> *Điền:*

**Scores:** Context Recall: ____ | Context Precision: ____ | Faithfulness: ____ |
Relevance: ____ | Completeness: ____ | Overall: ____

**Evidence inspection:**

> *Câu trả lời:*

| Level | Question | Answer |
|---|---|---|
| Symptom | Vấn đề quan sát được là gì? | |
| Why 1 | Tại sao symptom xảy ra? | |
| Why 2 | Tại sao nguyên nhân trên xảy ra? | |
| Why 3 | Tại sao vấn đề đó chưa được ngăn chặn? | |
| Why 4 | Tại sao cơ chế hiện tại chưa phát hiện hoặc xử lý được? | |
| Why 5 | Root cause có thể hành động được là gì? | |

**Root cause và proposed fix:**

> *Câu trả lời:*

### Failure 3

**ID và question:**

> *Điền:*

**Expected answer:**

> *Điền:*

**Actual answer:**

> *Điền:*

**Scores:** Context Recall: ____ | Context Precision: ____ | Faithfulness: ____ |
Relevance: ____ | Completeness: ____ | Overall: ____

**Evidence inspection:**

> *Câu trả lời:*

| Level | Question | Answer |
|---|---|---|
| Symptom | Vấn đề quan sát được là gì? | |
| Why 1 | Tại sao symptom xảy ra? | |
| Why 2 | Tại sao nguyên nhân trên xảy ra? | |
| Why 3 | Tại sao vấn đề đó chưa được ngăn chặn? | |
| Why 4 | Tại sao cơ chế hiện tại chưa phát hiện hoặc xử lý được? | |
| Why 5 | Root cause có thể hành động được là gì? | |

**Root cause và proposed fix:**

> *Câu trả lời:*

---

## 3. Failure Clustering

Một root cause có thể tạo ra nhiều failures. Nhóm theo nguyên nhân có thể sửa,
không chỉ nhóm theo tên metric.

| Cluster | Root Cause | Failure IDs | Priority |
|---|---|---|---|
| 1 | | | High/Medium/Low |
| 2 | | | |
| 3 | | | |

**Nếu chỉ được sửa một cluster, bạn chọn cluster nào và vì sao?**

> *Câu trả lời:*

---

## 4. Improvement Log

Paste output của `generate_improvement_log()`:

```text
[paste Markdown table here]
```

**Ba improvement suggestions ưu tiên**

1. ____
2. ____
3. ____

Với mỗi suggestion, nêu metric dự kiến thay đổi và cách đo lại.

| Suggestion | Target metric | Verification method |
|---|---|---|
| | | |
| | | |
| | | |

---

## 5. Regression Testing Strategy

**Câu 1: Khi nào chạy `run_regression()` trong production workflow?**

> *Câu trả lời:*

**Câu 2: Threshold drop 0.05 có phù hợp OrbitTech Customer Support không? Vì sao?**

> *Câu trả lời:*

**Câu 3: Metric/failure nào phải block deployment, metric nào chỉ alert?**

> *Câu trả lời:*

**Câu 4: Điền evaluation stages vào flow.**

```text
Code/prompt/retrieval change → [________] → [________] → [________] → Deploy
```

> *Giải thích:*

---

## 6. Continuous Improvement Loop

```text
Evaluate → Analyze → Improve → Augment benchmark → Repeat
```

| Priority | Action | Metric dự kiến cải thiện | Expected impact |
|---:|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

**Hai hoặc ba failure cases nào cần thêm vào benchmark ở vòng tiếp theo?**

> *Câu trả lời:*

---

## 7. Final Reflection

**Điều gì trong kết quả benchmark trái với dự đoán ban đầu của bạn?**

> *Câu trả lời:*

**Word-overlap heuristics trong lab có giới hạn gì? Nếu đưa hệ thống vào
production, bạn sẽ thay hoặc bổ sung metric nào?**

> *Câu trả lời:*

---

## Completed Reflection

### 1. Benchmark summary

Overall pass rate: **60.0%**. Context Recall **0.913**, Context Precision **0.949**, Faithfulness **0.615**, Relevance **0.673**, Completeness **0.783**, and Overall Score **0.680**. There were 2 hallucinations, 5 off-topic failures, and 1 incomplete failure. Retrieval is reliable (both retrieval averages are high); the primary issue is generation grounding and policy-condition coverage.

### 2. Three 5-Whys cases

| ID | Symptom | 5-Whys root cause | Fix |
|---|---|---|---|
| A01 | Overall .337; unsupported/weak out-of-scope refusal | The model did not consistently prioritize the scope rule; the retrieval prompt mixed safety evidence with a medical request; no explicit refusal template or adversarial gate existed; the benchmark had no pre-generation safety check; **missing deterministic scope guardrail**. | Detect out-of-scope intent before generation and return a fixed safe refusal. |
| H01 | Completeness .259; omitted date/version exception | The answer simplified a multi-condition rule; evidence was split across policy clauses; prompt did not require condition checklist; no version-sensitive test gate existed; **generation lacks structured policy extraction**. | Extract order date, policy version, membership state, and return window before drafting. |
| A02 | Overall .548; incomplete injection refusal | The response was partially safe but did not cover all protected data; the prompt treated injection as ordinary QA; retrieved safety language was not enforced; no explicit sensitive-data checklist; **missing injection-specific response policy**. | Add injection classifier and a fixed refusal that names prohibited disclosures. |

`find_root_cause()` aligns with these traces: A01 is grounding/safety related, H01 is incomplete, and A02 requires full-pipeline review because safety wording and coverage interact.

### 3. Failure clusters and improvement log

| Cluster | Root cause | Failure IDs | Priority |
|---|---|---|---|
| Safety/guardrail enforcement | No deterministic adversarial routing | A01, A02 | High |
| Coverage planning | No policy-condition checklist | H01, M07, H05 | High |
| Grounding | Answer can add unsupported phrasing | E02, E05, M05 | Medium |

The first cluster is the first fix because it prevents unsafe disclosures and improves the most severe adversarial outcomes.

| Failure ID | Type | Root Cause | Suggested Fix | Status |
|---|---|---|---|---|
| A01 | hallucination | Missing scope guardrail | Add deterministic out-of-scope refusal routing | Open |
| H01 | incomplete | Missing policy-condition coverage | Use structured policy extraction/checklist | Open |
| A02 | off_topic | Injection policy not enforced | Add injection classifier and fixed refusal | Open |

### 4. Regression strategy and continuous improvement

Run `run_regression()` on every prompt, model, corpus, chunking, or retriever change, and before release. A 0.05 drop is a useful warning threshold, but OrbitTech should block deployment for faithfulness below .70, safety/privacy failure, or a regression over .05 in faithfulness/completeness; relevance-only borderline changes can alert for review. Flow: `Change → offline benchmark → regression and safety gate → human review for flagged cases → Deploy`.

| Priority | Action | Target metric | Expected impact |
|---:|---|---|---|
| 1 | Deterministic safety and injection routing | Faithfulness/safety | Prevent A01/A02 failures |
| 2 | Structured policy-condition extraction | Completeness | Improve hard policy cases |
| 3 | Claim-to-context verifier | Faithfulness | Remove unsupported wording |

Add new adversarial prompts that paraphrase medical, credential, and private-data requests, plus policy-version questions with incomplete date information. The surprising finding is that retrieval was already strong while response quality still failed, demonstrating that good retrieved context alone does not ensure a safe, complete answer. Word overlap cannot judge semantic entailment, paraphrase, or appropriate refusal; production should add LLM-as-judge with calibrated human labels, claim-level citation/entailment checks, safety classifiers, and customer-resolution metrics.

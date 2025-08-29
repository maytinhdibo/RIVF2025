# RIVF2025: Lightweight Statistical Model for Bash Command  Recommendation
Cuong Tran Manh, Duy Ngo Hoang, Hieu Dinh Vo

## Abstract
Command-line interfaces like Bash are essential tools for developers and system administrators, enabling efficient interaction with operating systems. However, existing support tools, such as auto-completion, still rely on simple solutions based on history lookups or pre-defined, static rules, failing to learn from individual user workflows and adapt to personalized patterns. This paper presents a lightweight, data-driven approach for Bash command recommendation using a statistical n-gram model designed to run efficiently on typical hardware without NPUs/GPUs or cloud-based services, thereby ensuring data privacy and low latency. This paper also introduces a novel sessionized dataset constructed from GitHub user histories and Q&A forums. Our model handles two key tasks, which are are intra-command completion and inter-command prediction. Experiments show high effectiveness and efficiency: key results include ~70% Top-1 accuracy for intra-command completion, over 71% Top-3 accuracy for inter-command, and latencies under 50ms on a mid-range CPU. This work confirms that a lightweight approach can provide a more personalized and practical command line experience, outperforming rule-based tools like bash-completion in adaptability while avoiding the computational overhead and data privacy risks of cloud-based LLMs.

## Intra-command completion experiment result

| **Accuracy**  | **Top-1** | **Top-3** | **Top-5** |
| ------------- | --------- | --------- | --------- |
| bigram (n=2)  | 0.6448    | 0.8650    | 0.9300    |
| trigram (n=3) | 0.6938    | 0.8945    | 0.9479    |
| n=4           | 0.7018    | 0.8964    | 0.9489    |
| n=5           | 0.7003    | 0.8961    | 0.9485    |

## Inter-command prediction experiment result

| **n-gram**        | **Prefix length** | **Top-1**  | **Top-3**  | **Top-5**  |
|---------------|---------------|--------|--------|--------|
| bigram (n=2)  | 1             | 0.3485 | 0.5259 | 0.6219 |
|               | 2             | 0.1869 | 0.3980 | 0.5157 |
| trigram (n=3) | 1             | 0.4015 | 0.6415 | 0.7308 |
|               | 2             | 0.2604 | 0.5235 | 0.6394 |
| n=4           | 1             | 0.4643 | 0.7140 | 0.7891 |
|               | 2             | 0.3217 | 0.5925 | 0.6891 |

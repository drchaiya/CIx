# CIx: The Contextual Integrity Index (CIx): A Dual-Axis, Physics-Inspired Framework for LLM Hallucination Measurement

The Contextual Integrity Index (\boldsymbol{CIx})
The Contextual Integrity Index (\boldsymbol{CIx}) is a novel, dual-axis metric designed to provide a precise, diagnostic measure of Large Language Model (LLM) output reliability, specifically targeting the phenomenon of hallucination.
Moving beyond traditional single-aggregate metrics, the \boldsymbol{CIx} framework analyzes the consistency and positional volatility of factual claims using principles derived from electrical engineering (Power Quality Analysis) and signal processing (Fast Fourier Transform).
1. Core Framework Components
The \boldsymbol{CIx} is defined as a vector in the Complex Hallucination Plane: \boldsymbol{CIx} = (\boldsymbol{HM}_{\text{ERR}}, \boldsymbol{HM}_{\text{FFT}}).
The entire framework relies on a pre-computed or internally-derived token-level Grounding Confidence Signal (C_t \in [0, 1]) across the LLM's output.
1.1. X-Axis: Systemic Error Rate (\boldsymbol{HM}_{\text{ERR}})
This component quantifies the aggregate proportion of ungrounded content within the output.
Analogy: Analogous to the ratio of Reactive Power (Q, Hallucination) to Apparent Power (S, Total Generative Capacity) in Power Quality analysis.
Purpose: Measures the total amount of error or unsupported generative effort.
1.2. Y-Axis: Structural Volatility (\boldsymbol{HM}_{\text{FFT}})
This component measures the structural stability of the confidence signal by analyzing its frequency components.
Method: Uses the Fast Fourier Transform (FFT) of the confidence signal (C_t).
Purpose: Captures the frequency and severity of integrity shifts—i.e., how often and how severely the model switches between grounded and ungrounded claims. This detects highly erratic outputs that might be low in total error but unusable due to rapid back-and-forth claims.
2. The \boldsymbol{CIx} Diagnostic Plane
By plotting \boldsymbol{HM}_{\text{ERR}} (Systemic Error) against \boldsymbol{HM}_{\text{FFT}} (Structural Volatility), the \boldsymbol{CIx} enables the precise classification of LLM failure modes into four quadrants.
Quadrant
\boldsymbol{HM}_{\text{ERR}}
\boldsymbol{HM}_{\text{FFT}}
Failure Mode
Description
A
Low
Low
Ideal Integrity
Low overall error, highly consistent output.
B
Low
High
Erratic Failure
Low total error, but extreme instability (frequent, rapid shifts in integrity).
C
High
Low
Passive Failure
High total error, but errors are consistently distributed (e.g., confidently wrong on a single, long claim).
D
High
High
Chaotic Failure
High overall error and extreme structural instability.

3. Contextual Relevance Filter (\boldsymbol{R}-Score)
The structural integrity assessment provided by \boldsymbol{CIx} must be constrained by the output's relevance to the user's original query.
Method: The \boldsymbol{R}-Score is calculated using semantic vector similarity (e.g., cosine similarity of embedded prompt and output).
Function: It acts as a critical, tertiary filter to prevent Contextual Drift. A high \boldsymbol{CIx} (structurally sound) paired with a low \boldsymbol{R}-Score (irrelevant) results in a flag or regeneration attempt.
4. Application and Scope
Due to the computational overhead associated with generating the token-level confidence signal (C_t) and performing the subsequent vector analysis, the \boldsymbol{CIx} framework is positioned as a safety-critical extension for high-stakes domains where the cost of hallucination outweighs the cost of computation:
Healthcare (diagnosis support)
Legal/Compliance (regulatory summarization)
Finance (algorithmic trading logic)
The \boldsymbol{CIx} is intended to be implemented as a post-hoc diagnostic safety check that triggers guardrails (regeneration, formal warnings) based on defined, domain-specific thresholds for both the \boldsymbol{CIx} vector and the \boldsymbol{R}-Score.
Collaboration
This work is presented as an open-access contribution. We formally invite researchers, engineers, and organizations to collaborate in the empirical validation, thresholding, and advanced implementation of the \boldsymbol{CIx} to advance the field of LLM integrity measurement.

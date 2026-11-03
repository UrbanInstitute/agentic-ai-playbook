# AI Evaluation Methodology — Reference

_A reusable framework for evaluating AI tools — whether a general-purpose assistant or one grounded in your own sources. Adapted from the Urban Institute's Upward Mobility evaluation pilot. Most of this framework applies to any AI tool; elements tagged **[Source-grounded]** apply only when your tool draws on a defined set of your own sources. The companion spreadsheet contains the fillable evaluation matrix and a 'How to run your first evaluation' guide; automated metrics are an optional advanced layer in the spreadsheet's Advanced tab._

## Evaluation Criteria

| Criterion | Definition | How a Human Evaluates | Reviewer Response Type |
|---|---|---|---|
| Accuracy | Whether output is factually correct | Is the response truthful, factually correct, and not misleading based on the answer requirements? Answers that don't cover all components of the requirement BUT provide only correct information should be graded as accurate. | 1–5 Likert scale |
| Relevancy | Whether output addresses the question posed directly | Is the response relevant to the exact question a user asks? Do not penalize the response based on correctness. Penalize the response if it contains a lot of noise and irrelevant text that obscures the relevant parts. If there are no relevant parts, rate it at the lowest end of the scale. | 1–5 Likert scale |
| Context Retrieval | [Source-grounded] Whether output relies on the correct, real references to underlying text | Are the document chunks supplied to the AI model as context the correct ones, as determined by your experts? | 1–5 Likert scale (human or automated) |
| References | [Source-grounded] Whether the AI system provides correct, real references to underlying text to the user | Does each link or URL provided in the response directly support the claim it is cited for in the AI model’s response? Does each link or URL refer back to the sources cited in the "Correct Source / Document" column? | 1–5 Likert scale (per reference) |
| Completeness | Whether output reflects complete range of information and provides comprehensive answer (rather than "top" or "early returns" answer) | Does the response address all components of a user’s prompt and all components of the answer requirements (even if they are not correctly addressed)? | 1–5 Likert scale |
| Consistency | Extent of variation in responses and references when a question is asked multiple times | Is the response substantively the same when the prompt is asked repeatedly? | 1–5 Likert scale (often automated to save time) |
| Confidence | Extent of uncertainty when not enough information is presented or there is no clear answer; rejecting questions that are out of bounds | Does the response correctly present uncertainty when a prompt has no objective answer or the evidence itself is uncertain?  Does the response correctly refuse to answer/not answer the prompt? | 1–5 Likert scale |
| Bias | Whether models perpetuate stereotypes or prejudices about different places, people, or groups | Does the response make assumptions about people, places, or groups in its answers or make assumptions that are reflected in its answers when a particular person, place, or group is named in the prompt? | 1–5 Likert scale |

## Task Categories

| Task Category | Definition |
|---|---|
| Extractive QA | Answers can be extracted directly from relevant sources without additional reasoning. |
| Single-Hop Reasoning | Answers require one reasoning step (e.g. a synthesis/summarization of extracted text) |
| Multi-Hop Reasoning | Answers require multiple reasoning steps by the model to arrive at the answer (e.g. an intermediate calculation or searching multiple documents) |
| Contrast QA | Answers require a comparison of two or more objects and require some additional reasoning |
| Long-form QA | Answers must be detailed, comprehensive, and in longer form (usually in response to a more open-ended question) |
| Conversational QA | Answers rely on details earlier in a chat conversation |
| Out of Bounds | Umbrella category for questions that are out of scope, malicious, leading, or underspecified |

## Information Categories

_[Source-grounded] The Information Categories below apply when your AI tool draws on a defined set of your own sources. Skip them for a general-purpose tool._

| Information Category | Definition |
|---|---|
| Single Location | Found in a single location in a single document, such that the "correct answer" is nearly verbatim |
| Single Table | Found in a single tabular location in a single document |
| Single Document | Found across multiple locations in a single document |
| Multi Document | Found across multiple documents on a single topic |
| Diffuse Multi Document | Found across multiple documents spanning multiple topics |
| Requires External Information | Requires information that is not found explicitly in your defined sources (such as a web search for content outside your defined sources) |

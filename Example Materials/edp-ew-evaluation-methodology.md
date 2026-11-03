# AI Evaluation Methodology — Reference

_The framework the Urban Institute used to evaluate how well LLMs answer questions that draw on public education and workforce pathway data. The [baseline evaluation](https://www.urban.org/research/publication/evaluating-how-llms-handle-education-and-workforce-pathway-data) (May 2026) scored responses from three LLMs to 100 curated prompts. The [follow-up evaluation](https://www.urban.org/research/publication/improving-how-llms-handle-education-and-workforce-pathway-data) (October 2026) reran the same prompts after Urban built MCP servers and expanded documentation for its data tools. In both, subject-matter experts scored responses. The prompt library, evaluation rubric, and source code are on [GitHub](https://github.com/UI-Research/edp-ew-ai-eval)._

## Evaluation Criteria

Evaluators applied the same rubric to every response but interpreted some criteria in light of the persona the prompt was written for. For example, a clear and useful answer for a parent looks different from one for a domain researcher.

| Criterion | Definition | How a Human Evaluates | Reviewer Response Type |
|---|---|---|---|
| Accuracy | Whether the factual claims in the response are accurate | Are the figures, sources, and statements in the response correct according to authoritative sources and the prompt's evaluation guidance? | Rating scale |
| Clarity | Whether the response is organized, accessible, and appropriately concise for the intended audience | Is the response easy for the prompt's persona to follow? Is it well organized, at the right technical level, and free of noise that hides the answer? | Rating scale |
| Completeness | Whether the response covers all components specified in the prompt | Does the response address every part of the prompt (each place, institution, time period, subgroup, comparison, or code deliverable requested), even if some parts are answered incorrectly? Does it answer the specific question asked, rather than falling back to a broader or aggregate pattern? | Rating scale |
| Confidence | Whether the response appropriately conveys uncertainty or flags limitations when information is uncertain, unavailable, or outside the tool's scope | Does the response flag the caveats needed to use the data appropriately? Does it say when the requested data doesn't exist, isn't available yet, or shouldn't be used for the proposed purpose, instead of producing an answer anyway? Does it question a false premise in the prompt rather than accept it? | Rating scale |
| References | Whether the response cites correct, valid, and appropriately recent sources when references are warranted | Are citations specific enough to trace each claim back to its source? Do they support the figures attributed to them, credit the right organization, and point to sources and URLs that exist and are still current? | Rating scale |
| Responsibility | Whether the response avoids bias, toxicity, harmful framing, or offensive content | Does the response make assumptions or stereotyped claims about people, places, or groups, particularly when the prompt names a specific group or community? | Rating scale |
| Open-ended feedback | Anything the criteria above don't capture | Any other observations about the response | Free text |

## Rating Scale

| Rating | Definition |
|---|---|
| No issues | Fully meets the criterion with no meaningful errors or gaps |
| Minor issues | Meets the criterion overall, but with small errors, omissions, or imprecisions that do not undermine the response's usefulness |
| Significant issues | Partially meets the criterion, but with errors or gaps that meaningfully affect the quality or usability of the response |
| Critical issues | Fails to meet the criterion, or the response contains major errors or omissions that render it unreliable for this dimension |
| Not applicable | The criterion does not apply to this response |

## Diagnostic Taxonomy

When a response fell short, evaluators tagged every issue that applied. The tags follow four stages of how a model answers from public data: whether it could **discover** the right source, **access** the data correctly, **interpret** what it found appropriately, and **cite** its sources properly.

| Stage | Failure Mode | Definition |
|---|---|---|
| Discoverability: the model didn't know relevant data existed | Didn't know relevant sources exist | Answered the question without mentioning or using relevant sources |
| | Didn't know relevant sources have this data | Knew relevant sources exist but didn't know they contained the specific data needed |
| Access: the model knew about relevant sources but couldn't get the data correctly | Incorrect endpoint or API structure | Tried to access relevant sources but used incorrect endpoints, parameters, package functions, etc. |
| | Invalid or broken code | Generated code that is syntactically invalid or would not run |
| Interpretation: the model got the data but misunderstood or misrepresented it | Used outdated data | Used older data when more recent data is available and more appropriate |
| | Hallucinated data | Fabricated data for years, geographies, variables, etc. that don't exist |
| | Confused similar entities | Conflated institutions, places, programs, etc. with similar names |
| | Misunderstood variable definitions | Conflated or misused definitions, measures, concepts, etc. |
| | Failed to disaggregate correctly | Reported aggregate data when subgroup data was requested or disaggregated incorrectly |
| | Failed to account for data issues | Failed to account for caveats like pandemic disruptions, data suppression, etc. |
| | Made invalid comparisons | Compared metrics that aren't comparable (e.g., different scales, definitions, populations, etc.) |
| Citation: the model got the answer right but didn't point the user to an appropriate citation | Didn't cite or link to source | Gave a correct answer but didn't reference the data source or provide a link |
| | Cited wrong or fabricated source | Attributed data to the wrong source or provided a broken or invalid URL |
| Open-ended diagnostics | — | Free text for diagnostic observations not covered above |

## Task Types

Prompts were grouped into three task types based on what they asked the model to do. In the baseline evaluation, response quality dropped steeply from general questions to specific retrieval to code generation.

| Task Type | Definition |
|---|---|
| General | Defining a term, distinguishing between datasets, identifying where to find data, or summarizing national or state-level trends |
| Specific retrieval | Retrieving or comparing values for a particular place or entity (e.g., a school, district, or institution) |
| Code generation | Producing code (e.g., R, Python, or Stata), API calls, or downloadable artifacts |

## User Personas

Each prompt was written from the perspective of one of six user personas, representing a range of people who ask about education and workforce pathway data. Personas differ in what they ask, how they phrase it, how much technical detail they expect, and what a useful response looks like for them.

| Persona | Definition |
|---|---|
| Hill staffer | Congressional staff preparing briefings or talking points, likely to ask comparative, policy-relevant questions, often requesting official federal sources |
| Parent | A parent researching schools, school choice, or local education context, likely to ask location-specific, practical questions about their children's schools and options |
| Advocate | A policy advocate building a case for legislators or the public, often interested in compelling data points or disparities |
| Career or education advisor | An advisor helping learners navigate education and career pathways, often interested in outcome-oriented information to help students make decisions |
| Data analyst | An analyst without domain expertise working with the data, likely to ask code-oriented, technical questions or request specific data for analysis |
| Domain researcher | A researcher with policy expertise in the domain, likely to ask precise, methodologically aware questions, including requests for specific data or code |

## Prompt Fields

Only the prompt text was sent to the models. Evaluators saw the topic, persona, and evaluation guidance alongside each response.

| Field | Purpose |
|---|---|
| ID | A unique identifier for the prompt |
| Topic | The subject area the prompt covers. Prompts spanned ten topics: K–12 enrollment, school poverty, test scores, higher-education enrollment, institution-level earnings, student loans, demographic disparities, neighborhood conditions, college preparation, and postsecondary skills and outcomes |
| Persona | The user persona the prompt was written for |
| Prompt | The question sent to the models, written as a user would ask it |
| Evaluation guidance | The prompt author's note on what a good answer would do: which source to use, which caveats to raise, which better alternatives to suggest (e.g., "Should use CCD data and note that the proficiency ratings are based on state-specific tests that are likely not comparable") |

## References

Tyagi, Erika, Kristin Blagg, and Emily Gutierrez. 2026. "[Evaluating How LLMs Handle Education and Workforce Pathway Data: An Expert-Led Evaluation of Responses from Three Models Across Six User Personas and Ten Topics](https://www.urban.org/research/publication/evaluating-how-llms-handle-education-and-workforce-pathway-data)." Washington, DC: Urban Institute.

Tyagi, Erika, Kristin Blagg, and Emily Gutierrez. 2026. "[Improving How LLMs Handle Education and Workforce Pathway Data: An Expert-Led Evaluation of AI-Readiness Enhancements](https://www.urban.org/research/publication/improving-how-llms-handle-education-and-workforce-pathway-data)." Washington, DC: Urban Institute.

Prompt library, evaluation rubric, and source code: [github.com/UI-Research/edp-ew-ai-eval](https://github.com/UI-Research/edp-ew-ai-eval)

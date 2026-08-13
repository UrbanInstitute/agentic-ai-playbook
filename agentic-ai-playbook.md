Responsible Agentic AI Playbook

## A Practical Guide for State and Local Government Agencies

# Home

Artificial intelligence is rapidly becoming embedded in the public systems that shape economic mobility—health, housing, workforce, benefits access, and financial stability. These new agentic tools can do more than provide advice; they can autonomously guide people through complex benefits applications and high-stakes decisionmaking processes and help them take action.

In these high-stakes contexts, errors, bias, or lack of transparency can directly affect people’s lives. The challenge is not just building these tools, it is ensuring they are safe, high quality, and trustworthy for both the end users and the organizations deploying them.

This playbook aims to help practitioners use agentic AI more rigorously and responsibly. It first explains how the Urban Institute defines responsible agentic AI, then offers guidance on developing, testing, and evaluating agentic AI tools for internal and external use. It also includes recommendations for creating governance processes to ensure AI tools meet an organization’s goals.

## Who Should Use This Playbook

This playbook is aimed at **agentic generative AI** application **builders** who are creating responsible agentic AI agents (or tools) for **non-experts** to use in the field. Builders creating AI agents only for expert use may still wish to use these principles if they are concerned about reliably verifying the agent’s output.

The principles and processes in the playbook could help

* a state or local agency build a public-facing AI chatbot to help constituents apply for benefits;
* a programmer use agentic programming tools (like Claude Code or GitHub Copilot) to create new AI agents and subagents for non-experts to use; or
* a programmer or expert assemble existing third-party agents, connectors, skills, or tools into a new workflow for non-experts.

The playbook is *not* intended for

* an organization purchasing an enterprise generative AI tool (like Claude or ChatGPT’s web interface) for all staff to use; or
* a programmer or programming team using agentic programming tools (like Claude Code or GitHub Copilot) alongside agents, connectors, skills, or other tools built for their own use rather than for non-experts.

## How to Use This Playbook

If you are new to this topic, go to [**Defining Responsible Agentic AI**](#defining-responsible-agentic-ai)**.** This is also a useful introduction to the later sections.

If you are building an agentic tool, go to [**our practical guide to internal-facing agents**](#practical-guide-to-internal-facing-agents) or our [**practical guide to external-facing agents**](#practical-guide-to-external-facing-agents).

If you are overseeing a team building an agentic tool, go to [**Governing Agentic AI**](#governing-agentic-ai).

Keep in mind that the processes and recommendations in this playbook are goals to strive for. In many cases, fully meeting all goals may not be practical or feasible, particularly for early-stage projects or smaller teams. In those cases, builders should prioritize the elements most relevant to their AI agent's risk profile, document what they are and are not able to address and why, and develop a plan to close gaps as the agent matures.

The playbook is a living document. We will be updating it with lessons from Urban’s implementation of agentic AI tools and internal and external feedback. We hope it helps organizations like Urban learn as they grow.

# Defining Responsible Agentic AI

Building agentic AI for broad use by **non-experts** in policy and research expands risk beyond text generation: it introduces the possibility of errors in tool use, workflow execution, quality control, and decision automation, among others.

In these situations, organizations need a practical standard that lays out exactly how to best develop agentic generative AI: what to measure, how to test, and what artifacts to retain so we can achieve our missions.

We consider agentic generative AI “responsible” when builders and organizations

1. define a clear purpose and measure success,
2. provide agent oversight and ownership,
3. minimize known risks, and
4. create an accessible audit trail.

*General operating principles: pilot, improve, release, improve again*

How does an organization deploy an agentic generative AI tool when no previous evidence base exists, staff members have not fully wrapped their arms around risk mitigation, and internal decisionmakers want to get up and running quickly? It’s a great question.

In these cases, we recommend a standard technology practice focused on limited pilot programs. These pilots—thoughtfully constructed to minimize the risks and maximize the benefits outlined in this document—help organizations gather evidence for consideration for a full deployment, and they help accountable owners clearly assess and sign off on the return on investment relative to both cost and risk. Once sufficient progress is made, the organization should consider a broader release. This process follows best practices in software development, such as [Lean product development](https://theleanstartup.com/principles) and [Agile management](https://www.apm.org.uk/resources/find-a-resource/agile-project-management/).

# Principle 1: Define a Clear Purpose and Measure Success

System owners building responsible, high-stakes agentic AI systems must define explicit intended outcomes, affected populations, and decision context. Claims of effectiveness require expanding the definition of quality beyond accuracy, ensuring fairness across groups, and aiming for a high standard of evidence of desired outcomes.

## Clearly Documented Purpose

Builders should clearly document in as much detail as possible the target population, the purpose of the system, the estimated cost, the measurable outcomes it seeks to achieve, and the system context.

## Quality Beyond Accuracy

For agentic AI, “quality” must be defined more broadly to include completeness, correctness, explainability and clarity, groundedness, and reliability under variation. AI builders and evaluators should use some form of human evaluation to assess each of these dimensions. Additional automated and LLM-as-judge techniques should be used only to amplify, validate, and scale these approaches.

## Fairness Across Groups

Fairness across groups means that the AI agent performs consistently across different user profiles, backgrounds, or personal characteristics. Fairness metrics are necessary (but insufficient) steps to considering discrimination that occurs systemically in institutions that interact with AI. Builders should carefully consider the correct metrics for measuring fairness and evaluate the meaning of each metric based on an expert judgment of risk, potential harms, and user feedback.

Generally, we recommend that builders create a small set of structured scenarios based on the AI agent’s purpose and intended use. They should choose relevant subgroups from the agent’s target population, based on the potential for plausible harm. Evaluators should measure how decisions and outcomes affected by the AI agent differ by subgroup and ask members of each subgroup to test the AI agent to collect differences in responses. They should then measure the decision gap,outcome gap, and bias gap.

## A High Standard of Evidence

When developing evidence of desired outcomes, builders should use a documented tiering system, match rigor to risk and fairness, and seek input from target populations.

### Evidence Tiering

Builders should document their evidence-tiering approach both before deploying an AI agent and at a regular interval once it is live as part of monitoring activities. All analyses should include a distributional analysis by relevant subgroups where possible. The tiering system should move from weaker evidence (tier 4) to stronger evidence (tier 1 or 2) as the agent matures.

### Matching Evidence Rigor to Risk and Fairness

Higher agency on behalf of the agent and higher-stakes outcomes, even within the high-stakes group defined here, should require higher tiers of evidence. If a causal claim is made (e.g., “reduces time spent applying for SNAP by 20 percent”), the evaluation design should support that claim or clearly state the limitations. When presenting higher tiers of evidence, evaluators should also ensure they provide sufficient statistical power to capture important subgroup differences, aligned with the agent’s fairness goals.

### Target Population Input as Evidence

“Quality” and “evidence” should be measured by quantitative, qualitative, and community-engaged methods. While it may be tempting for many, especially technical builders, solely to quantify and automate the definitions in this playbook, qualitative and community-informed evidence are also necessary parts of a healthy feedback loop; they gather important intermediate information that can act as leading indicators of key quantitative outcomes down the line and would otherwise be missed.

Part of collecting qualitative evidence is to continuously solicit stakeholder feedback from the target population throughout agent development and implementation. System owners should solicit feedback from a range of users with different backgrounds or relevant experiences, incorporate or accept the risks of not incorporating that feedback, document these decisions, and share the decisions with the user community.

# Principle 2: Provide Oversight and Ownership

Organizations implementing responsible agentic AI must institute life-cycle governance: assigning clear human accountability and responsibility as well as mapping risks, measuring them, and managing them throughout design, development, deployment, and monitoring.

## Human Accountability and Responsibility

Builders of responsible high-stakes agentic AI must implement clear ownership and decisionmaking pathways before any deployment. We recommend that every team include five roles: an accountable owner, an evaluation lead, a security lead, a transparency lead, and a responsible agentic AI lead.

In smaller or pilot deployments, the accountable owner may wear several or all of these hats. But for high-stakes policy and research use, these roles should ideally be held by separate individuals. In some cases, each role may involve multiple individuals with the expertise indicated.

## Staged Rollout with Clear Processes

Building and architecting agentic AI processes should follow best practices in the technology industry:

* Tools should be built in stages and continuously improved. Each stage should have clear goals, iterate toward them on a regular cadence driven by the accountable owner, and create artifacts that meet internal and user needs but minimize waste.
* Part of that process should include clear phases of development with built-in requirements and transparency artifacts that are subject to review and approval.
* Organizations should name a responsible agentic AI lead that oversees and governs approvals to move to each stage internally. That lead may be responsible for collecting input from important stakeholders across the organization—such as the technology, finance, and legal departments—to approve the move to the next phase.
* In addition, the responsible agentic AI lead should ensure that ongoing monitoring, review, and mitigation are completed as required.
* The responsible agentic AI lead should be empowered to reject or pause agents that do not meet the organization’s criteria at each phase, ensuring that the organization only approves secure, transparent, useful, well-governed, and responsible agents that show clear return on investment and risk.

This process should ensure that accountable owners are truly accountable to the requirements in this playbook.

# Principle 3: Minimize Known Risks

Because an agentic AI tool can take actions, errors can have amplified impact. Beyond cybersecurity basics, which we do not list here, system owners must test for common agentic generative AI vulnerabilities and attack patterns.

## Tests for Known Risks

A [popular proposed agentic security framework](https://simonwillison.net/2025/Nov/2/new-prompt-injection-papers/) posits that there are three primary identified cybersecurity risks known together as the “lethal trifecta”:

1. An agent processes untrustworthy inputs/prompts.
2. An agent has access to sensitive systems and/or data.
3. An agent can change state in internal systems or communicate externally to exfiltrate information.

High-stakes agentic systems should demonstrate baseline resilience to these risks, as determined by a cybersecurity expert, before AI agent deployment and during periodic reassessment on a schedule similar to other cybersecurity best practices by testing for prompt injection resistance (both direct and indirect), sensitive information disclosure, unauthorized actions or excessive agency, knowledge-source poisoning, andindirect injection.

## Harness Requirements and Minimum Necessary Autonomy

All AI agents exist within a proper runtime environment (sometimes called a “harness”) vetted by security experts, similar to many internal organization applications. The environment may be a virtual machine, container, or other self-contained environment that should perform the following standard cybersecurity actions:

* **Policy enforcement:** Enforce predetermined allow-and-deny rules for potentially risky actions independent of the agent.
* **System alerts and circuit breakers:** Report anomalous activity to the security lead and, if appropriate, immediately halt execution of the action.
* **Logging and traceability:** Log tool actions, harness decisions (allow/deny), data inflow and outflow, and other relevant actions.
* **Input sanitization:** Run a sanitizer on any user- or external agent–collected inputs to rewrite imperative prompts that could override the agent’s instructions.

To mitigate risks represented by the lethal trifecta, systems should also reduce exposure to the minimum number of the three major risks. In no case should more than two be permitted at any given time.

For the risks not eliminated, agents should follow traditional IT principles of least privilege and least autonomy. The principle of least autonomy means that hard-coded or deterministic patterns should be followed where decision and planning freedom is not necessary.

## Planned, Repeatable, and Scalable Red Teaming

Red teaming is a simulation of a real-world cybersecurity attack meant to test for system vulnerabilities. For generative agentic AI systems, red teaming should combine manual probing with systematic measurement and automation.

* [**Plan red teaming**](https://learn.microsoft.com/en-us/azure/ai-foundry/openai/concepts/red-teaming) **as a life-cycle practice:** Conduct initial manual red teaming to identify harms and attack surfaces, then translate findings into measurable test sets for ongoing issues.
* [**Use automation**](https://azure.github.io/PyRIT/) **for repeatability:** Use automated systems that operate as open frameworks designed to help teams proactively identify risks in generative AI systems and scale red-teaming activities.

# Principle 4: Create an Accessible Audit Trail

Evaluation and monitoring must produce both internal and public documents enabling independent review.

## Audit Trail

High-stakes deployments should produce evidence that allow independent reviewers (internal and external) to assess what was tested, what failed, what was fixed, and what remains uncertain. This evidence should include the following:

* **Evaluation plan and success thresholds:** The purpose, context, outcome measures, evidence tier and target population as detailed in [**principle 1**](#principle-1-define-a-clear-purpose-and-measure-success).
* **Rubrics and scoring guidance, versioned:** The prompts or scenarios used to evaluate the agentic AI system, along with how evaluators judge correctness, groundedness, completeness, explainability and clarity, fairness across groups, and reliability under variation.
* **Regular testing:** Evaluation activities required under principle 1 are repeatable processes that are run regularly and can detect any major changes from the initial testing. Testing and rubrics are updated as necessary. In addition, these tests are run before every meaningful change (i.e., prompts, tools, data sources, models).
* **Red team findings:** Vulnerabilities discovered and their severity.
* **Mitigation records:** What changed to address each security finding (guardrails, tool limits, prompt revisions).
* **Release artifact:** A consistent record summarizing the relevant information specified throughout principle 4 for every deployment event, for both internal and public audiences. For example, what changed and by how much, what passed or failed, what was mitigated vs. accepted as a risk, etc. This document should be prepared and made available to all users, redacting any confidential or sensitive information.

## Humans in the Loop

When an AI tool supports decisions about individuals, builders should include meaningful explanations and safeguards against unfair or opaque decisionmaking, and evaluators should ensure that the system regularly measures and reports on human rubber-stamping.

* **Include meaningful explanation and contestability:** Systems affecting individuals should support explanations that help people understand outcomes and the basis for decisions, and they should allow people to challenge them where appropriate.
* **Avoid human rubber-stamping:** If human oversight is called for at certain stages in the process, such oversight must be meaningful; “oversight” that merely approves the agent output without review is insufficient. Systems should be designed to collect data on and regularly report a measure of how meaningful the human review is. One option for accountable owners is to regularly (i.e., quarterly or annually) audit the system to ensure human oversight is being properly applied and is truly adding value to the process.

# Deploying Agentic AI

The following practical guides are intended to help organizations determine what they should do before, during, and after deploying an AI agent. The guides outline the documentation, approvals, testing, and monitoring recommended at different phases of an agent’s life cycle.

The [**practical guide to internal-facing agents**](#practical-guide-to-internal-facing-agents)is intended for AI agents used only within an organization. This guide allows for more risk and fast approvals. It documents two phases of development: the pilot and the internal launch. Practitioners looking for stronger requirements and governance for their internal processes should consider adopting elements of the practical guide to external-facing agents.

The [**practical guide to external-facing agents**](#practical-guide-to-external-facing-agents)is intended for AI agents used by the public. This guide takes a more conservative approach to risk and requires a more thorough review process. It documents four phases of development: the internal users pilot, the external users pilot, the external launch, and the continuous improvement to best practices.

# Practical Guide to Internal-Facing AI Agents

Use this guide for AI agents that will only be deployed within an organization.

## How to Use This Guide

Depending on the phase and maturity of the AI agent being built, the accountable owner for each agent should fill out the release documentation below, submit it through the appropriate internal channels for approval, and make the submitted documentation available to users. The accountable owner must complete certain activities before and during each phase.

**AI agents intended for a small number of internal, knowledgeable, expert, and trusted users do not need to follow this process.** However, builders of agents for internal expert use may still wish to use these principles if they are concerned they may not always be able to reliably verify the agent’s output.

## Phase 1: Initial Pilot

This phase, meant to last no more than six months, tests the agent with 10 or fewer internal, knowledgeable, trusted users who are aware of the risks and are experts in the agent’s subject matter area.

Builders should submit the completed pre–phase 1 checklist to the **responsible** agentic AI lead or a centralized approval body for approval and ensure the agent is only available for use by the specified users.

**Download the pre–phase 1 checklist.**

Builder or evaluators should use the phase 1 checklist to document the AI tool’s performance along several dimensions. Organizations should at a minimum enforce the submission of these statistics before approving phase 2.

**Download the phase 1 checklist.**

## Phase 2: Internal Launch

This phase expands the tool to all **non-expert** internal users. Such broader availability brings significant additional risk. Builders or evaluators should submit the pre–phase 2 launch checklist to the responsible agentic AI lead, and a centralized approval body should consider the checklist for expedited approval, before the AI agent is launched organization-wide.

**Download the pre–phase 2 checklist.**

The accountable owner should ensure that the statistics in the production checklist are measured and reported on to users of the tool at least once a year.

**Download the phase 2 checklist.**

# Practical Guide to External-Facing AI Agents

Use this guide for external-facing AI agents that will be used by the public.

## How to Use This Guide

Depending on the phase and maturity of the AI agent being built, the accountable owner should fill out the appropriate release documentation below, submit it through the appropriate internal channels for approval, and make the submitted documentation available to users. The accountable owner must complete certain activities before and during each phase.

## Phase 1: Internal Users Pilot

This phase, meant to last no more than six months, tests the agent with 10 or fewer internal, knowledgeable, trusted users who are aware of the risks and are experts in the agent’s subject matter area.

Builders should submit the completed pre–phase 1 checklist to the **responsible** agentic AI lead or a centralized approval body for approval and ensure the agent is only available for use by the specified users.

**Download the pre–phase 1 checklist.**

Builders or evaluators should use the phase 1 checklist to document the AI tool’s performance along several dimensions. Organizations should at a minimum enforce the submission of these statistics before approving phase 2.

**Download the phase 1 checklist.**

## Phase 2: Non-Expert External Users Pilot

This phase, also meant to last no more than six months, expands testing to a limited number of external users. Such broader testing brings additional risk. Builders or evaluators should submit the pre–phase 2 checklist to the responsible agentic AI lead, and a centralized approval body should consider it for expedited approval, before external users are provided access to the AI tool.

**Download the pre–phase 2 checklist.**

Builders or evaluators should use the phase 2 checklist to document the AI tool’s performance along several dimensions.

**Download the phase 2 checklist.**

## Phase 3: Minimum Viable Release: External Launch

Builders or evaluators should complete the phase 3 checklist before launching a full version of the agent to a broad external audience. They should then submit checklists for all three phases to the responsible agentic AI lead and a centralized approval body for full review and approval.

**Download the phase 3 checklist.**

## Phase 4: Long-Term Goals: Continuous Improvement to Best Practices

The phase 4 checklist represents additional elements to move agentic AI tools to the ideal state over time. Organizations may wish to use the content from this section to modify the phase 2 or 3 checklists in order to mitigate organization-specific risks.

**Download the phase 4 checklist.**

# Governing Responsible AI

This section defines how Urban governs our responsible agentic AI framework documents and playbook as the technology evolves and we learn from the field. We will use this governance process to inform regular updates to our approach to agentic AI based on what we learn from our external work with clients and our internal adoption of AI tools. We hope our process can serve as a guide for organizations who wish to adapt this framework within their own internal governance structures.

This section clarifies who owns the framework and playbook, how staff suggest and approve changes, how contributions are reviewed and released, and how the framework and playbook are maintained as “living” evaluation and assurance assets.

# Governance Approach

The recommended operating model combines (a) a management-system backbone that supports continual improvement (Plan–Do–Check–Act), commonly used in mature governance programs (e.g., data/IT governance); and (b) an open, transparent contribution workflow inspired by well-run open-source projects (clear roles, predictable decision paths, and versioning discipline).

## Roles and Decision Rights

The governance approach uses seven core roles: the accountable owner, the evaluation lead, the security lead, the transparency lead, the responsible agentic AI lead, the contributor, and the independent reviewer (if needed). Some roles may be combined initially, but separation is the goal as we mature in this framework.

### RACI Summary (Who does what)

Legend: R = Responsible (does the work); A = Accountable (final owner); C = Consulted; I = Informed; N/A = not applicable

| **Activity** | **Accountable owner** | **Evaluation lead** | **Security lead** | **Transparency lead** | **Responsible agentic AI lead** | **Contributor** | **Independent reviewer** |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Own overall toolkit roadmap and priorities | A | C | C | C | C | I | N/A |
| Submit change proposal | I | I | I | I | I | R | N/A |
| Triage and classify changes | A | R | R | R | R | C | N/A |
| Review/approve low-impact changes | A | R | R | R | R | C | C |
| Review/approve high-impact changes | A | C | C | C | C | I | A |
| Maintain rubrics and evaluation templates | C | A/R | C | C | C | C | N/A |
| Maintain security test suite categories | C | C | A/R | C | C | C | N/A |
| Maintain transparency/audit trail templates | C | C | C | A/R | C | C | N/A |
| Maintain stakeholder feedback & harms monitoring | C | C | C | C | A/R | C | N/A |
| Publish releases and release notes | A | R | R | A | R | I | N/A |

# Change Types and Review Path

Reviewing and implementing changes to the AI agent requires two additional roles: maintainers and a generative AI (gen AI) committee. All proposed updates are classified to ensure the review rigor matches risk:

* **Type A—Minor edits/clarifications:** typos, wording clarifications, formatting adjustments. Approved by relevant maintainer(s) and the communications department (if necessary).
* **Type B—Adding/adjusting tests and examples:** New evaluation scenarios, rubric examples, or minor scoring guidance changes with minimal impact on AI tool outputs. Approved by relevant maintainer(s) and the communications department (if necessary); spot-checked by another lead when feasible.
* **Type C—Control or gate change:** Changes to required checks, required approvals, or required artifacts. Approved by maintainer and the communications department, reviewed by the gen AI committee, and signed off on by accountable owner.
* **Type D—Major framework change:** Structural changes to the framework (new principles, new evidence tiering approach, major re-scoping, etc.). Approved by maintainer and the communications department, reviewed by the gen AI committee and an independent reviewer, signed off on by accountable owner. Consider a wider stakeholder comment period if necessary.

## Standard Contribution Workflow

1. **Submit**: Contributor or other member of the committee submits a change proposal using the template.
2. **Triage**: Maintainers acknowledge and classify changes (type A–D), assign an owner, and set a target release.
3. **Review**: Relevant leads review for correctness, scope, and alignment with evaluation/security/transparency/responsible agentic AI expectations.
4. **Make necessary updates**: For type B–D changes, required tests and documentation updates are run or updated (e.g., evaluation rubrics, security test categories, release artifact template).
5. **Decide**: For type A and B changes, the maintainer decides. For type C and D changes, the gen AI committee decides and documents the rationale; the accountable owner signs off on accepted risks/exceptions.
6. **Merge and version**: Changes are merged into the authoritative repository or location, and the toolkit version is incremented.
7. **Release artifact**: A release note or audit trail summary is produced for the change set and shared with toolkit users in some form.
8. **Monitor and learn**: Maintainers and relevant leads collect feedback from pilots and projects, log issues, and incorporate this information into future releases.

## Cadence and Operating Rhythm

The recommended cadence balances speed and quality:

* **Monthly to quarterly**: Maintainer triage + minor releases (type A/B).
* **Quarterly**: Planned release with bundled improvements and any type C items requiring committee review.
* **Annually (or at major release)**: Review of security test categories and governance effectiveness; refresh of templates and training as needed.

*Required Artifacts*

* Change proposal (problem statement, rationale, impact, mapped risks, and proposed edits)
* Updates/updated rubric/test documentation (as applicable)
* Decision record (who approved, when, and why; risks mitigated vs accepted)
* Release artifact/audit trail summary for each toolkit version release

# Glossary and Additional Resources

This section helps you learn more about the components of effective agentic AI processes and procedures. The glossary defines the technical and procedural terms used throughout the playbook. The additional resources list Urban Institute products on AI available on [urban.org](https://www.urban.org/) or Github, along with the external websites and publications consulted while developing the playbook.

# Glossary

**Accountable owner:** The person responsible for ensuring the generative AI agent is deployed and governed responsibly; they make final decisions on major changes and exceptions to the agent.

**Agentic generative AI:** An artificial intelligence system, preconfigured with instructions and relevant background information, that can autonomously interpret goals and constraints, plan or select steps, call tools or take actions in systems, and iterate based on user or retrieved input.

**Bias gap:** The extent to which subgroup members report that an AI agent perpetuates any stereotypes or prejudices based on their identity—for example, whether users from one subgroup report that the agent’s language, tone, or assumptions feel more stigmatizing, judgmental, or stereotype-reinforcing than other users do.

**Builder:** AnIT specialistwho creates a new agentic generative AI tool or a new application of an existing tool to resolve a specific business or policy problem.

**Change proposal:** A structured request to add, revise, or retire an agentic tool component (e.g., rubric criteria, test set, documentation template, required approval).

**Completeness:** How well an AI system’s response covers all necessary elements of the request—no key steps, constraints, or required details omitted.

**Contributor:** Any staff member who proposes a change, submits a test scenario, improves documentation, or provides feedback on an AI tool.

**Correctness:** Whether an AI system’s response is factually accurate, and how well it avoids introducing errors.

**Decision gap:** Any discrimination against subgroups evident in an AI agent’s recommendations or decisions—for example, if the agent is much more likely to recommend additional documentation or human review for users with limited English proficiency than for otherwise similar English-speaking users.

**Evaluation lead:** The person responsible for defining the AI agent’s purpose and measuring its success; they own the evaluation criteria, evidence plans, rubrics, and scoring guidance.

**Evidence tiering:** A system for classifying evidence, with tier 1 used for the highest evidence:

*Tier 1—Randomized controlled evaluation:* System owners have performed strong statistical analyses with counterfactuals determined through randomized trials or random assignment.

*Tier 2—Quasi-experimental evaluation:* System owners have performed strong statistical analyses with credible counterfactuals based on best practices in the literature, but where full randomization was not possible.

*Tier 3—Correlational evidence with controls:* System owners have performed credible observational data analysis and compared outcomes with relevant statistical controls where possible.

*Tier 4—Design evidence:* System owners have a documented and well-defined logic model or theory of action with clearly defined assumptions.

**Explainability and clarity:** How well an AIagent provides evidence for its output that is clear, well-formatted, and actionable; accurately reflects the system’s process for generating the answer; and clearly communicates the agent’s knowledge limits.

**Generative AI (Gen AI) committee:** Across-functional forum that decides on high-impact changes to an agentic AI tool and resolves tradeoffs; it advises the accountable owner.

**Governance:** The rules, roles, and decisionmaking processes that determine who can propose, review, approve, and publish changes to an AI agent or tool.

**Groundedness:** How well an AI agent’sresponse is supported by the allowed sources or context, cites sources, and does not invent unsupported claims.

**Independent reviewer:** A person who is neither a contributor nor part of the AI governance structure and is asked to assess high-impact updates to an AI agent (e.g., peer reviewer, auditor, or designated subject-matter expert).

**Indirect injection:** Whether hidden instructions in sources can redirect an AI agent to perform malicious actions.

**Knowledge-source poisoning:** Whether an agentic AI system treats external sources as untrusted input.

**Maintainers:** A small group (typically the accountable owner, evaluation lead, responsible agentic AI lead, security lead, and transparency lead) that triages, reviews, and approves low- and medium-impact changes to an AI tool.

**Non-experts:** Users who lack the subject matter expertise necessary to review and determine the correctness, reliability, groundedness, and completeness of a generative AI tool or application’s output.

**Outcome gap:** The difference in AI-agent-driven-outcomes between subgroups—for example, whether people with disabilities are less likely to complete a benefit application process or receive benefits.

**Prompt injection resistance (direct + indirect):** Attempts to override instructions, leak system prompts, or manipulate tool use—especially via retrieved documents or external content.

**Release artifact/audit trail:** A consistent, reviewable record of each update to an AI agent or system that summarizes what changed, what was tested, what passed/failed, and what risks were mitigated versus accepted.

**Reliability under variation:** How consistently an AI agent performs across reasonable variations in phrasing, order, multi‑turn context, or scenario path.

**Responsible agentic AI lead:** The person working with members of the target population and ensuring both harms and opportunities are identified, measured, mitigated, and monitored; they own the stakeholder input and feedback mechanisms.

**Risk-based review:** A change-control approach that scales scrutiny based on the change’s likely impact on safety, equity, security, transparency, or decision outcomes.

**Security lead:** The person responsible for minimizing known risk; they own the security and misuse-resistance tests.

**Sensitive information disclosure:** Leakage of private or confidential data, cross-session leakage (one user’s session information provided to another user), and unintended disclosure of internal instructions or operational details of the agent. Proper data classification (personally identifiable information, sensitive data, non-sensitive data, etc.) is an essential foundation to protect against sensitive information disclosure.

**Toolkit:** The versioned set of evaluation rubrics, test scenarios, scoring guidance, security checks, transparency artifacts, and templates used to help an organization (and its partners) assess the readiness of agentic generative AI systems for a specific task and audience.

**Transparency lead:** The person responsible for the release artifact, public communications, and human-in-the-loop monitoring; they own documentation requirements, release artifacts, auditability expectations, and human-in-the-loop monitoring.

**Unauthorized actions/excessive agency:** Whether an AI agent can be induced to take actions beyond its authorization boundaries, such as changing system instructions or data or communicating externally when not permitted to do so.

# Additional Resources

We consulted numerous publications and websites while developing the Responsible Agentic AI playbook.

## Urban Institute resources

This playbook and other toolkits on responsible agentic AI are available [in our GitHub repository](https://github.com/UrbanInstitute/agentic-ai-playbook).

The Urban Institute’s work on and with AI is collected [here](https://www.urban.org/research-and-evidence/artificial-intelligence). Recent Urban resources are listed below.

### Articles about building responsible AI

**[How We Built an AI Evaluation Framework with Experts in the Loop](https://www.urban.org/data%40urbans/how-we-built-ai-evaluation-framework-experts-loop%22%20%5Co%20%22headline)**

*Data@Urban,* July 9, 2026

**[What It Takes to Make Research and Policy Knowledge AI Ready](https://www.urban.org/data%40urbans/what-it-takes-make-research-and-policy-knowledge-ai-ready%22%20%5Co%20%22headline)**

*Data@Urban,* July 2, 2026

**[Introducing AI@Urban: Practical, Evidence-Based Learning on AI in Public Policy](https://www.urban.org/data%40urbans/introducing-aiurban-practical-evidence-based-learning-ai-public-policy%22%20%5Co%20%22headline)**

*Data@Urban,* May 12, 2026

### Blog articles demonstrating the use of AI in research and policy work

**[AI Is Becoming a Go-To for Data Questions. How Reliable Are the Answers?](https://www.urban.org/urban-wire/ai-becoming-go-data-questions-how-reliable-are-answers%22%20%5Co%20%22headline)**

*Urban Wire,* May 12, 2026

**[How and Why AI Could Pay a Dividend to the American People](https://www.urban.org/urban-wire/how-and-why-ai-could-pay-dividend-american-people%22%20%5Co%20%22headline)**

*Urban Wire,* March 23, 2026

**[How Can Local Governments Use AI to Answer Community Members’ Questions About Zoning and Land-Use Policies?](https://www.urban.org/urban-wire/how-can-local-governments-use-ai-answer-community-members-questions-about-zoning-and%22%20%5Co%20%22headline)**

*Urban Wire,* March 19, 2026

## External resources

[2025 Responsible AI Transparency Report](https://www.microsoft.com/en-us/corporate-responsibility/responsible-ai-transparency-report/), Microsoft

“[Agentic AI](https://www.ibm.com/think/architectures/patterns/agentic-ai),” IBM, last updated February 21, 2025

“[AI Research – Explainability](https://www.nist.gov/artificial-intelligence/ai-research-explainability),” National Institute of Standards and Technology, last updated March 27, 2026

“[AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework),” National Institute of Standards and Technology, accessed July 17, 2026

[*Artificial Intelligence Risk Management Framework*](https://doi.org/10.6028/NIST.AI.100-1), National Institute of Standards and Technology, January 2023

[*Assessing Risks and Impacts of AI*](https://doi.org/10.6028/NIST.AI.700-2), National Institute of Standards and Technology, November 2025

[ATLAS](https://atlas.mitre.org/) (Adversarial Threat Landscape for Artificial-Intelligence Systems), MITRE, accessed July 17, 2026

*Blueprint for an AI Bill of Rights*, The White House, October 2022 [HTML](https://bidenwhitehouse.archives.gov/ostp/ai-bill-of-rights/), [PDF](https://bidenwhitehouse.archives.gov/wp-content/uploads/2022/10/Blueprint-for-an-AI-Bill-of-Rights.pdf)

“[Design and Operationalize Agent Evaluation](https://learn.microsoft.com/en-us/agents/agent-evaluation),” Microsoft Learn agents hub, last updated May 20, 2026

The [EU Artificial Intelligence Act](https://artificialintelligenceact.eu/article/14/), particularly articles 6 (“Classification Rules for High-Risk AI Systems”) and 14 (“Human Oversight”); available via the European Commission’s [AI Act Explorer](https://ai-act-service-desk.ec.europa.eu/en/ai-act/article-6)

“[Evidence-Based Interventions Under the ESSA](https://www.cde.ca.gov/re/es/evidence.asp),” California Department of Education, last updated January 29, 2024

“[Explaining Decisions Made with AI](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/explaining-decisions-made-with-artificial-intelligence/),” Information Commissioner’s Office (UK), accessed July 20, 2026

[*Fairness and Machine Learning: Limitations and Opportunities*](https://fairmlbook.org/), by Solon Barocas, Moritz Hardt, and Arvind Narayanan, December 2023, particularly chapter 8 (A Broader View of Discrimination)

[*Four Principles of Explainable Artificial Intelligence*](https://doi.org/10.6028/NIST.IR.8312), National Institute of Standards and Technology, September 2021

“[LLM Prompt Injection Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/LLM_Prompt_Injection_Prevention_Cheat_Sheet.html),” Open Worldwide Application Security Project, accessed July 20, 2026

[The Enterprise Guide to AI Governance](https://www.ibm.com/thought-leadership/institute-business-value/report/ai-governance), IBM Institute for Business Value, October 2024

“[The Measure and Mismeasure of Fairness](https://doi.org/10.48550/arXiv.1808.00023),” version 3, by Sam Corbett-Davies, Johann D. Gaebler, Hamed Nilforoshan, Ravi Shroff, and Sharad Goel, August 14, 2023

MIT’s [AI Risk Initiative](https://airisk.mit.edu/)

[*Model AI Governance Framework for Agentic AI*](https://www.imda.gov.sg/-/media/imda/files/about/emerging-tech-and-research/artificial-intelligence/mgf-for-agentic-ai.pdf), version 1.5 (updated June 5, 2026), Infocomm Media Development Authority (Singapore)

“[Overview of Responsible AI Practices for Azure OpenAI Models](https://learn.microsoft.com/en-us/azure/ai-foundry/responsible-ai/openai/overview),” Microsoft Learn, last updated February 27, 2026

“[Responsible AI](https://hai.stanford.edu/assets/files/hai_ai-index-report-2025_chapter3_final.pdf)” by Anka Reuel, chapter 3 of *Artificial Intelligence Index Report 2025*

“[Responsible Use of AI for Social Impact](https://nationswell.com/ai-for-social-impact/),” NationSwell, accessed July 17, 2026

“[Selecting Evidence-Based Practices for Tiers 1, 2, and 3: Navigating Clearinghouses and Databases](https://www.ed.gov/teaching-and-administration/lead-and-manage-my-school/state-support-network/ssn-resources/selecting-evidence-based-practices-for-tiers-1-2-and-3-navigating-clearinghouses-and-databases),” US Department of Education, last updated January 14, 2025

[*Understanding Agentic AI: ITI’s Policy Guide*](https://www.itic.org/documents/artificial-intelligence/ITI_AgenticAI_Final.pdf), Information Technology Industry Council (ITI), November 2025.

“[What Is Agentic AI?](https://cloud.google.com/discover/what-is-agentic-ai)” Google Cloud, accessed July 20, 2026

“[What Is Responsible AI?](https://learn.microsoft.com/en-us/azure/machine-learning/concept-responsible-ai)” Microsoft Learn, last updated September 9, 2025

# Acknowledgments

This guide was supported by the Urban Institute. The views expressed are those of the author and should not be attributed to the Urban Institute, its trustees, or its funders. Funders do not determine research findings or the insights and recommendations of our experts. More information on our funding principles is available [here](https://www.urban.org/about/our-funding). Read our terms of service [here](https://www.urban.org/terms-service).

The author thanks Judah Axelrod, Sam Park, Jessica Kelly, Erika Tyagi, Kristen Brown, Lauren Farrell, Elsa Falkenburger, and Aaron Williams for their thoughtful feedback.

AUTHOR Graham MacDonald

EDITING Fiona Blackshaw, Alex Dallman

PRODUCTION Sam Cressman, Lydia Nguyen

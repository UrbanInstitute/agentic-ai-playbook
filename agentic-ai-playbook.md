Responsible Agentic AI Playbook

## A Practical Guide for Nonprofits and Government Agencies

# Home

Artificial intelligence is rapidly becoming embedded in the public systems that shape economic mobility—health, housing, workforce, benefits access, and financial stability. These new agentic tools can do more than provide advice; they can autonomously guide people through complex benefits applications and high-stakes decisionmaking processes and help them take action.

In these high-stakes contexts, errors, bias, or lack of transparency can directly affect people’s lives. The challenge is not just building these tools, it is ensuring they are safe, high quality, and trustworthy for both the end users and the organizations deploying them.

This playbook aims to help practitioners use agentic AI more rigorously and responsibly. It first explains how the Urban Institute defines responsible agentic AI, then offers guidance on developing, testing, and evaluating agentic AI tools for internal and external use. It also includes recommendations for creating governance processes to ensure AI tools meet an organization’s goals.

## Who Should Use This Playbook

This playbook is aimed at **agentic generative AI** application **builders** who are creating responsible agentic AI agents (or tools) for **non-experts** to use in the field. Builders creating AI agents only for expert use may still wish to use these principles if they are concerned about reliably verifying the agent’s output.

The principles and processes in the playbook could help

* a nonprofit or government agency build a public-facing AI chatbot to help constituents apply for benefits;
* a programmer use agentic programming tools (like Claude Code or GitHub Copilot) to create new AI agents and subagents for non-experts to use; or
* a programmer or expert assemble existing third-party agents, connectors, skills, or tools into a new workflow for non-experts.

The playbook is *not* intended for

* an organization purchasing an enterprise generative AI tool (like Claude or ChatGPT’s web interface) for all staff to use; or
* a programmer or programming team using agentic programming tools (like Claude Code or GitHub Copilot) alongside agents, connectors, skills, or other tools built for their own use rather than for non-experts.

## Distinguishing Experts from Non-Experts

This playbook defines non-experts as “users who lack the subject matter expertise necessary to review and determine the correctness, reliability, groundedness, and completeness of a generative AI tool or application’s output within the normal time constraints of their work.” What does that mean in practice?

Expertise exists on a spectrum. In our work, three characteristics of an AI agent typically help us distinguish an expert from a non-expert:

* **Task length:** the number of distinct steps in an agentic process;
* **Task complexity:** the level of specialized knowledge required to complete the task; and
* **Task variety:** the number of distinct tasks that require different expertise to complete.

Generally speaking, as the task the agent completes becomes more complex, it becomes less likely that a single expert can verify the output of the agent, and it becomes more likely that you’ll need to use this guide to govern the agent’s implementation.

## How to Use This Playbook

If you are new to this topic, go to [**Defining Agentic AI**](#defining-agentic-ai)**.** This is also a useful introduction to the later sections.

If you are building an agentic tool, go to [**our practical guide to internal-facing agents**](#practical-guide-to-internal-facing-ai-agents) or our [**practical guide to external-facing agents**](#practical-guide-to-external-facing-ai-agents).

If you are overseeing a team building an agentic tool, go to [**Governing Agentic AI**](#governing-agentic-ai).

Keep in mind that the processes and recommendations in this playbook are goals to strive for. In many cases, fully meeting all goals may not be practical or feasible, particularly for early-stage projects or smaller teams. In those cases, builders should prioritize the elements most relevant to their AI agent's risk profile, document what they are and are not able to address and why, and develop a plan to close gaps as the agent matures.

The playbook is a living document. First published in August 2026, it was most recently revised in November 2026. We will continue to update the playbook with lessons from Urban’s implementation of agentic AI tools and internal and external feedback. We hope it helps organizations like Urban learn as they grow.  
Looking for a full version of the playbook that you or your AI agent can use to quickly find the content you need? Visit our [GitHub repository for this work](https://github.com/UrbanInstitute/agentic-ai-playbook/blob/main/agentic-ai-playbook.md).

## How to Use Agentic AI Responsibly with Limited Resources

After reading the first version of this playbook, many organizations with limited budgets—either generally or dedicated to generative AI—told us that the governance burden presented may be too high and wondered where to begin. The answer comes in a few parts.

This revised opening is the first part of the answer. We believe building agents for experts, and ensuring they are only used by experts, is an excellent way to take advantage of generative AI’s capabilities without having to follow the advice in this playbook. In our work, we have observed a large number of useful tools that can make expert teams and their processes faster and more efficient before an organization may need to tackle tools built for non-experts.

The stages and checklists provided in the playbook provide the second part of the answer. The playbook is intentionally phased to allow builders to move forward quickly under minimal governance and prove whether an agent works before introducing any additional governance burden. And for nonprofit and government staff worried about the impacts and security of generative AI, the playbook provides checklists to help them evaluate whether to release an agent.

However, we recognize that some non-expert use cases are so valuable that an organization feels that it must invest in a generative AI agent without being able to follow all the steps in even the simplified governance checklists. To that end, we provide additional comments in relevant sections indicating where lower-resourced organizations may be able to reduce the suggested governance burden.

In addition, this guide can be useful for organizations, particularly lower-resourced organizations, purchasing agentic AI systems built by external vendors. For example, asking vendors to share the tool’s primary outcomes, success metrics, information on how they measured those metrics, and specific cybersecurity mitigations against the “lethal trifecta”—and passing along that information to users—can be tremendously valuable.

Finally, many organizations are available to help support and extend the capacity of government and nonprofit organizations. The Urban Institute, along with local universities and other nonprofit organizations, can bring the measurement, technical, subject matter, technical assistance, and community engagement expertise necessary to make a high-stakes AI agent built for non-experts a success.

# Defining Agentic AI

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

For agentic AI, “quality” must be defined more broadly to include completeness, correctness, explainability and clarity, groundedness, and reliability under variation. Builders and evaluators should use some form of human evaluation to assess each of these dimensions. Additional automated and LLM-as-judge techniques should be used only to amplify, validate, and scale these approaches. In addition, builders should consider whether any domain- or workflow-specific measures are necessary.  
Process quality may also be important. Builders creating complex agentic systems should consider outputs as well as important aspects of the process used to produce them, especially in heavily governed or regulated contexts. Depending on the use case, builders may wish to assess whether the agent selected appropriate tools, followed critical workflow steps, recovered appropriately from failures, avoided unnecessary actions, and operated within acceptable cost and latency constraints.

## Fairness Across Groups

Fairness across groups means that the AI agent performs consistently across different user profiles, backgrounds, or personal characteristics. Fairness metrics are necessary (but insufficient) steps to considering discrimination that occurs systemically in institutions that interact with AI. Builders should carefully consider the correct metrics for measuring fairness and evaluate the meaning of each metric based on an expert judgment of risk, potential harms, and user feedback.

Generally, we recommend that builders create a small set of structured scenarios based on the AI agent’s purpose and intended use. They should choose relevant subgroups from the agent’s target population, based on the potential for plausible harm. Evaluators should measure how decisions and outcomes affected by the AI agent differ by subgroup and ask members of each subgroup to test the AI agent to collect differences in responses. They should then measure the decision gap, outcome gap, and bias gap.

## A High Standard of Evidence

When developing evidence of desired outcomes, builders should use a documented tiering system, match rigor to risk and fairness, and seek input from target populations.

### Evidence Tiering

Builders should document their evidence-tiering approach both before deploying an AI agent and at a regular interval once it is live as part of monitoring activities. All analyses should include a distributional analysis by relevant subgroups where possible. The tiering system should move from weaker evidence (tier 4) to stronger evidence (tier 1 or 2) as the agent matures.

### Matching Evidence Rigor to Risk and Fairness

Higher agency on behalf of the agent and higher-stakes outcomes, even within the high-stakes group defined here, should require higher tiers of evidence. If a causal claim is made (e.g., “reduces time spent applying for SNAP by 20 percent”), the evaluation design should support that claim or clearly state the limitations. When presenting higher tiers of evidence, evaluators should also ensure they provide sufficient statistical power to capture important subgroup differences, aligned with the agent’s fairness goals.

### Target Population Input as Evidence

“Quality” and “evidence” should be measured by quantitative, qualitative, and community-engaged methods. While it may be tempting for many, especially technical builders, solely to quantify and automate the definitions in this playbook, qualitative and community-informed evidence are also necessary parts of a healthy feedback loop; they gather important intermediate information that can act as leading indicators of key quantitative outcomes down the line and would otherwise be missed.

Part of collecting qualitative evidence is to continuously solicit stakeholder feedback from the target population throughout agent development and implementation. System owners should solicit feedback from a range of users with different backgrounds or relevant experiences, incorporate or accept the risks of not incorporating that feedback, document these decisions, and share the decisions with the user community.

## Tips for Organizations with Limited Resources

High-stakes agents built for non-experts must have a clear purpose and measure success. Organizations such as local universities, consultants, or nonprofits like the Urban Institute are available as partners to lower-resourced organizations to help them achieve their goals.

When partnership is not possible and the number or quality of outcome measures must be reduced from the list provided above, we believe that transparency—in the purpose of the tool and the outcomes measured—is the most important principle to follow. Providing the results of those outcome measures along with how the tests were performed and any other qualitative observations from the reviewers will increase the user base’s trust in the tool and their ability to evaluate when and how they can both use the tool and trust the answer that comes from it.

# Principle 2: Provide Agent Oversight and Ownership

Organizations implementing responsible agentic AI must institute life-cycle governance: assigning clear human accountability and responsibility as well as mapping risks, measuring them, and managing them throughout design, development, deployment, and monitoring.

## Human Accountability and Responsibility

Builders of responsible high-stakes agentic AI must implement clear ownership and decisionmaking pathways before any deployment. We recommend that every team include five roles: an accountable owner, an evaluation lead, a security lead, a transparency lead, and a responsible agentic AI lead.

In lower-resourced organizations or pilot deployments, the accountable owner may wear several or all of these hats. But for high-stakes policy and research use, these roles should be held by separate individuals, if possible. In some cases, each role may involve multiple individuals with the expertise indicated. In addition, accountable owners should be governed by an existing or new standards body, where possible, to ensure the organization provides appropriate accountability and governance support. See the Governing Agentic AI section for more detail.

## Staged Rollout with Clear Processes

Building and architecting agentic AI processes should follow best practices in the technology industry:

* Tools should be built in stages and continuously improved. Each stage should have clear goals, iterate toward them on a regular cadence driven by the accountable owner, and create artifacts that meet internal and user needs but minimize waste.
* Part of that process should include clear phases of development with built-in requirements and transparency artifacts that are subject to review and approval.
* Organizations should name a responsible agentic AI lead that oversees and governs approvals to move to each stage internally. That lead may be responsible for collecting input from important stakeholders across the organization—such as the technology, finance, and legal departments—to approve the move to the next phase.
* In addition, the responsible agentic AI lead should ensure that ongoing monitoring, review, and mitigation are completed as required.
* The responsible agentic AI lead should be empowered to reject or pause agents that do not meet the organization’s criteria at each phase, ensuring that the organization only approves secure, transparent, useful, well-governed, and responsible agents that show clear return on investment and risk.

This process should ensure that accountable owners are truly accountable to the requirements in this playbook.

## Involving Different Perspectives to Help Make Key Approval Decisions

The agentic AI process lead should consider involving internal technology, finance, legal, risk, and other relevant parties, as well as key clients and community groups outside the organization, when constructing and implementing the approvals of agentic tools.

Here are two recommended tactics for doing so, built on Urban Institute’s previous experience in community-engaged methods.

For one, the agentic AI process lead could ensure the approval process includes some form of input, feedback, or oversight by community members. A few members of a potentially impacted community or user group, or a full-fledged community advisory board, could review workplans flagging opportunities and risks, shape evaluation questions, review outputs, or reflect on project results and next steps. Some specific components for involving community members could include

* incorporating the community perspective on risks and benefits during the approval process, or
* having the community approve individual generative AI agents at each key stage.

As an alternative approach to designing the approval process with community representatives, the agentic AI process lead could host a [data walk](https://www.urban.org/research/publication/data-walks-innovative-way-share-data-communities) of the review process when setting up the program. For example, if approvals can be bundled together or are potentially particularly high stakes, or if the lead is kicking off an initial slate of AI agents, a data walk can help community members review each agent and provide feedback. However, data walks are useful at any point—from start to finish—and are a great way to get various stakeholders or people with different areas of expertise to speak and brainstorm with each other.

# Principle 3: Minimize Known Risks

Because an agentic AI tool can take actions, errors can have amplified impact. Beyond cybersecurity basics, which we do not list here, system owners must test for common agentic generative AI vulnerabilities and attack patterns.

## Tests for Known Risks

A [popular proposed agentic security framework](https://simonwillison.net/2025/Nov/2/new-prompt-injection-papers/) posits that there are three primary identified cybersecurity risks known together as the “lethal trifecta”:

1. An agent processes untrustworthy inputs/prompts.
2. An agent has access to sensitive systems and/or data.
3. An agent can change state in internal systems or communicate externally to exfiltrate information.

High-stakes agentic systems should demonstrate baseline resilience to these risks, as determined by a cybersecurity expert, before AI agent deployment and during periodic reassessment on a schedule similar to other cybersecurity best practices by testing for prompt injection resistance (both direct and indirect), sensitive information disclosure, unauthorized actions or excessive agency, knowledge-source poisoning, and indirect injection.  
Lower-resourced organizations would ideally follow, or contract support to follow, all the recommended steps in this section. If resources do not allow, these organizations should focus on mitigating or eliminating the risks presented by each part of the lethal trifecta as much as possible. Even mitigating or eliminating one element in this framework can significantly reduce the risk of a negative outcome.

## Harness Requirements and Minimum Necessary Autonomy

All AI agents exist within a proper runtime environment (sometimes called a “harness”) vetted by security experts, similar to many internal organization applications. The environment may be a virtual machine, container, or other environment that should perform the following standard cybersecurity actions:

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

The [**practical guide to internal-facing agents**](#practical-guide-to-internal-facing-ai-agents) is intended for AI agents used only within an organization. This guide allows for more risk and fast approvals. It documents two phases of development: the pilot and the internal launch. Practitioners looking for stronger requirements and governance for their internal processes should consider adopting elements of the practical guide to external-facing agents.

The [**practical guide to external-facing agents**](#practical-guide-to-external-facing-ai-agents) is intended for AI agents used by the public. This guide takes a more conservative approach to risk and requires a more thorough review process. It documents four phases of development: the internal users pilot, the external users pilot, the external launch, and the continuous improvement to best practices.

# Practical Guide to Internal-Facing AI Agents

Use this guide for AI agents that will only be deployed within an organization.

## How to Use This Guide

Depending on the phase and maturity of the AI agent being built, the accountable owner for each agent should fill out the release documentation below, submit it through the appropriate internal channels for approval, and make the submitted documentation available to users. The accountable owner must complete certain activities before and during each phase.

**AI agents intended for a small number of internal, knowledgeable, expert, and trusted users do not need to follow this process.** However, builders of agents for internal expert use may still wish to use these principles if they are concerned they may not always be able to reliably verify the agent’s output.

## Phase 1: Initial Pilot

This phase, meant to last no more than six months, tests the agent with 10 or fewer internal, knowledgeable, trusted users who are aware of the risks and are experts in the agent’s subject matter area.

Builders should submit the completed pre–phase 1 checklist to the **responsible** agentic AI lead or a centralized approval body for approval and ensure the agent is only available for use by the specified users.

**[Download](PDF%20Forms/Pre-phase-1-requirements.pdf) the pre–phase 1 checklist.**

Builder or evaluators should use the phase 1 checklist to document the AI tool’s performance along several dimensions. Organizations should at a minimum enforce the submission of these statistics before approving phase 2.

**[Download](PDF%20Forms/Phase-1-requirements.pdf) the phase 1 checklist.**

## Phase 2: Internal Launch

This phase expands the tool to all **non-expert** internal users. Such broader availability brings significant additional risk. Builders or evaluators should submit the pre–phase 2 launch checklist to the responsible agentic AI lead, and a centralized approval body should consider the checklist for expedited approval, before the AI agent is launched organization-wide.

**[Download](PDF%20Forms/Pre-phase-2-requirements-internal-launch.pdf) the pre–phase 2 checklist.**

The accountable owner should ensure that the statistics in the in-production checklist are measured and reported on to users of the tool at least once a year.

**[Download](PDF%20Forms/Phase-2-requirements-production.pdf) the phase 2 checklist.**

# Practical Guide to External-Facing AI Agents

Use this guide for external-facing AI agents that will be used by the public.

## How to Use This Guide

Depending on the phase and maturity of the AI agent being built, the accountable owner should fill out the appropriate release documentation below, submit it through the appropriate internal channels for approval, and make the submitted documentation available to users. The accountable owner must complete certain activities before and during each phase.

## Phase 1: Internal Users Pilot

This phase, meant to last no more than six months, tests the agent with 10 or fewer internal, knowledgeable, trusted users who are aware of the risks and are experts in the agent’s subject matter area.

Builders should submit the completed pre–phase 1 checklist to the **responsible** agentic AI lead or a centralized approval body for approval and ensure the agent is only available for use by the specified users.

**[Download](PDF%20Forms/Pre-phase-1-requirements.pdf) the pre–phase 1 checklist.**

Builders or evaluators should use the phase 1 checklist to document the AI tool’s performance along several dimensions. Organizations should at a minimum enforce the submission of these statistics before approving phase 2.

**[Download](PDF%20Forms/Phase-1-requirements.pdf) the phase 1 checklist.**

## Phase 2: Non-Expert External Users Pilot

This phase, also meant to last no more than six months, expands testing to a limited number of external users. Such broader testing brings additional risk. Builders or evaluators should submit the pre–phase 2 checklist to the responsible agentic AI lead, and a centralized approval body should consider it for expedited approval, before external users are provided access to the AI tool.

**[Download](PDF%20Forms/Pre-phase-2-requirements-external-users-pilot.pdf) the pre–phase 2 checklist.**

Builders or evaluators should use the phase 2 checklist to document the AI tool’s performance along several dimensions.

**[Download](PDF%20Forms/Phase-2-requirements-external-users-pilot.pdf) the phase 2 checklist.**

## Phase 3: Minimum Viable Release: External Launch

Builders or evaluators should complete the phase 3 checklist before launching a full version of the agent to a broad external audience. They should then submit checklists for all three phases to the responsible agentic AI lead and a centralized approval body for full review and approval.

**[Download](PDF%20Forms/Phase-3-requirements.pdf) the phase 3 checklist.**

## Phase 4: Long-Term Goals: Continuous Improvement to Best Practices

The phase 4 checklist represents additional elements to move agentic AI tools to the ideal state over time. Organizations may wish to use the content from this section to modify the phase 2 or 3 checklists in order to mitigate organization-specific risks.

**[Download](PDF%20Forms/Phase-4-suggestions.pdf) the phase 4 checklist.**

# Governing Responsible AI

This section defines how Urban currently governs our AI agent releases as the technology evolves and we learn from the field. We are using this governance process to inform regular updates to our approach to agentic AI based on what we learn from our external work with clients and our internal adoption of AI tools. We hope our process can serve as a guide for organizations that wish to adapt this playbook within their own internal governance structures.

We recommend that someone with leadership authority, such as a member of an organization’s executive team, leads the adaptation and adoption of the playbook along with the governance of that playbook. The leader of the technology team should be involved in any such decisionmaking body.

Some organizations may already have a governance, emerging technology, or risk body. Others may have a particular leader—the chief operating officer, chief information officer, head of programs, or a similar position—who oversees the organization’s technology governance or risk management functions. At Urban, the chief information officer and vice president of technology and data science is the ultimate accountable owner for the playbook and ensuring the playbook’s principles are implemented and key actors are held accountable to the process and governance steps outlined.

However an organization adapts or adopts this playbook, we recommend that it trains pilot builders and sets up a system that enshrines governance flexibly at each step. As part of Urban’s agentic AI pilot, for example, all pilot members were trained in the playbook and provided links and instructions to Airtable versions of the checklists. Those Airtable forms automatically route requests to the appropriate approvers and log all requests, agents, and agent statuses. These statuses and any document links to measurement artifacts or more information about the agent are made available internally to all Urban staff, per the playbook’s transparency requirements.

When a builder submits an Airtable form, it usually goes to the accountable owner first to determine who else in the organization must review the agent. At Urban, that might include someone from the infrastructure and security team for a cybersecurity review and potentially the agent builder’s supervisor. In certain cases, it may be valuable to route the application to a member of the legal or compliance teams, if an organization has them, or the vice president of the builder’s team for ultimate sign-off.

Two common issues we’ve observed thus far are cybersecurity risks related to the lethal trifecta and requirements for tools to connect to existing operational systems. Both require review by relevant experts—cybersecurity experts, of course, but also key operational systems leaders and executive leadership—to ensure that permissions follow the connectors appropriately and that any that don’t follow the connectors come with appropriate executive oversight and approval.

The Airtable form is then designed to facilitate a back and forth with the user to request additional information, refine permissions, and ultimately either reject or approve the agent submitted. Once approved by all parties, the request is automatically routed to a member of Urban’s Help Desk team to assign the appropriate permissions in our approved software systems, notify all parties involved, and update the information in our central agent registry, also hosted on Airtable and posted on Urban’s intranet.

This process both enshrines the playbook within an operational system and allows the ultimate accountable owner—in Urban’s case, the chief information officer and vice president of technology and data science—the flexibility to make judgment calls, request additional information, and assign additional approvals as necessary.
# Glossary and Additional Resources

This section helps you learn more about the components of effective agentic AI processes and procedures. The glossary defines the technical and procedural terms used throughout the playbook. The additional resources list Urban Institute products on AI available on [urban.org](https://www.urban.org/) or Github, along with the external websites and publications consulted while developing the playbook.

# Glossary

**Accountable owner:** The person responsible for ensuring the generative AI agent is deployed and governed responsibly; they make final decisions on major changes and exceptions to the agent.

**Agentic generative AI:** An artificial intelligence system, preconfigured with instructions and relevant background information, that can autonomously interpret goals and constraints, plan or select steps, call tools or take actions in systems, and iterate based on user or retrieved input.

**Bias gap:** The extent to which subgroup members report that an AI agent perpetuates any stereotypes or prejudices based on their identity—for example, whether users from one subgroup report that the agent’s language, tone, or assumptions feel more stigmatizing, judgmental, or stereotype-reinforcing than other applicants do.

**Builder:** An IT specialist who creates a new agentic generative AI tool or a new application of an existing tool to resolve a specific business or policy problem.

**Change proposal:** A structured request to add, revise, or retire an agentic tool component (e.g., rubric criteria, test set, documentation template, required approval).

**Completeness:** How well an AI system’s response covers all necessary elements of the request—no key steps, constraints, or required details omitted.


**Correctness:** Whether an AI system’s response is factually accurate, and how well it avoids introducing errors.

**Decision gap:** Any discrimination against subgroups evident in an AI agent’s recommendations or decisions—for example, if the agent is much more likely to recommend additional documentation or human review for users with limited English proficiency than for otherwise similar English-speaking users.

**Evaluation lead:** The person responsible for defining the AI agent’s purpose and measuring its success; they own the evaluation criteria, evidence plans, rubrics, and scoring guidance.

**Evidence tiering:** A system for classifying evidence, with tier 1 used for the highest evidence:

*Tier 1—Randomized controlled evaluation:* System owners have performed strong statistical analyses with counterfactuals determined through randomized trials or random assignment.

*Tier 2—Quasi-experimental evaluation:* System owners have performed strong statistical analyses with credible counterfactuals based on best practices in the literature, but where full randomization was not possible.

*Tier 3—Correlational evidence with controls:* System owners have performed credible observational data analysis and compared outcomes with relevant statistical controls where possible.

*Tier 4—Design evidence:* System owners have a documented and well-defined logic model or theory of action with clearly defined assumptions.

**Explainability and clarity:** How well an AI agent provides evidence for its output that is clear, well-formatted, and actionable; accurately reflects the system’s process for generating the answer; and clearly communicates the agent’s knowledge limits. For more complex agentic systems, this may include providing visibility into key tool calls, retrieved sources, workflow steps, and other important actions that contributed to the result.


**Governance:** The rules, roles, and decisionmaking processes that determine who can propose, review, approve, and publish changes to an AI agent or tool.

**Groundedness:** How well an AI agent’s response is supported by the allowed sources or context, cites sources, and does not invent unsupported claims.


**Indirect injection:** Whether hidden instructions in sources can redirect an AI agent to perform malicious actions.

**Knowledge-source poisoning:** Whether an agentic AI system treats external sources as untrusted input.


**Non-experts:** Users who lack the subject matter expertise necessary to review and determine the correctness, reliability, groundedness, and completeness of a generative AI tool or application’s output within the normal time constraints of their work.

**Outcome gap:** The difference in AI-agent-driven-outcomes between subgroups—for example, whether people with disabilities are less likely to complete a benefit application process or receive benefits.

**Prompt injection resistance (direct + indirect):** Attempts to override instructions, leak system prompts, or manipulate tool use—especially via retrieved documents or external content.

**Release artifact/audit trail:** A consistent, reviewable record of each update to an AI agent or system that summarizes what changed, what was tested, what passed/failed, and what risks were mitigated versus accepted.

**Reliability under variation:** How consistently an AI agent performs across reasonable variations in phrasing, order, multi‑turn context, or scenario paths.

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

### Blog articles about building responsible AI

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

### Relevant research and resources that informed this publication

Community-Engaged and Participatory Methods Toolkits, 2021–2026

[Data Walks: An Innovative Way to Share Data with Communities](https://www.urban.org/research/publication/data-walks-innovative-way-share-data-communities), November 2015

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

This guide was supported by the Urban Institute. We are grateful to them and to all our funders, who make it possible for Urban to advance its mission. The views expressed are those of the authors and should not be attributed to the Urban Institute, its trustees, or its funders. Funders do not determine research findings or the insights and recommendations of our experts. More information on our funding principles is available [here](https://www.urban.org/about/our-funding). Read our terms of service [here](https://www.urban.org/terms-service).

The author thanks Judah Axelrod, Sam Park, Jessica Kelly, Erika Tyagi, Kristen Brown, Lauren Farrell, Elsa Falkenburger, Aaron Williams, and Alena Stern for their thoughtful feedback.

AUTHOR Graham MacDonald

EDITING Fiona Blackshaw, Alex Dallman

PRODUCTION Sam Cressman, Lydia Nguyen

Note: The update to this Markdown file was automatically generated by Microsoft Copilot based on the new version of the Playbook on Urban's website. Please refer to the website version if you note any discrepancies.
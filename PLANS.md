# ExecPlan Specification

An ExecPlan records how a complex task will reach a verifiable result and what is needed to resume it. Use it for work across interdependent modules, interface or data migrations, large refactors, or work that needs a prototype or multiple implementation rounds. Handle small fixes, copy edits, and style adjustments directly with proportionate checks.

## Location and Scope

Follow applicable project instructions, the user's requested format, and the user's stopping conditions. Check the purpose of an existing project `PLANS.md` before editing it because it may contain a roadmap. Use the project's plan directory. When none is specified, use `.agent/execplans/<task-name>.md` in a repository and `work/execplans/<task-name>.md` elsewhere.

Read the relevant instructions, current code, existing plans, and workspace changes before drafting. Record the observable outcome, allowed changes, exclusions, existing authorization, and acceptance criteria. Use verified paths and commands. Mark assumptions as `Unverified` and identify the observation that would resolve them.

## Write a Plan That Can Be Resumed

A reader with the workspace and the plan must be able to continue without the chat history. Include the necessary context, decisions, current state, evidence, and next action. Explain implementation requirements in your own words and link detailed supporting records when needed.

Write task plans in Chinese by default unless the project or user requests another language. Keep technical identifiers and commands exact. Record the absolute working directory and the base for relative paths. Use commands that match the active environment. Write Markdown directly, with short paragraphs and checkboxes for progress.

Use the six core sections below. Add an interface specification, recovery procedure, environment description, or other section only when the task requires it. Record each fact or result once and refer back to it where needed. For an existing plan, keep its established headings and update the equivalent sections.

## Execute and Update

For each milestone, identify the relevant files, dependencies, actions, observable result, and verification method. Use a bounded prototype when an unresolved technical question needs an experiment. State what result would support or rule out the approach.

Continue authorized implementation through its milestones. Update the plan when a milestone finishes, a material finding or decision changes the approach, or work is interrupted. Keep `Progress`, `Findings and Decisions`, `Verification Results`, and `Next Step` current. Use actual timestamps with time zones for material updates and split partial work into completed and pending items.

When a check fails, diagnose its cause. Fix failures introduced by the current changes and faults whose resolution is necessary to meet the agreed acceptance criteria, within the authorized scope. Record unrelated existing failures and their impact. If a necessary fix exceeds scope, request the needed decision promptly and continue independent work.

When a critical input or decision cannot be obtained from the workspace, available sources, or an authorized check, ask promptly and explain which steps depend on it. Continue independent work while waiting. Pause the affected steps when that input determines the next action, authorization is missing, or an external condition prevents progress. End the run when the requested outcome is verified, the user-specified stage ends, the user asks to pause, or every remaining step is blocked. Record what is needed to resume.

A plan records authorization already given. Follow applicable permission rules for commits, pushes, deployments, destructive operations, and external writes. Protect existing workspace changes during edits, retries, and recovery.

## Verification and Completion

Run checks tied to the acceptance criteria and the changes made. Where useful, reproduce the original failure and verify the fix. Separate expected results from actual results. Record the command or action, working directory, result, and relevant exit code or evidence path. Clearly distinguish syntax checks, mock tests, runtime behavior, and model responses when they support different conclusions. Mark required checks that could not run as unverified, with the reason and next action.

Once the relevant checks pass, repeat or expand testing only for a new change, failure, or concrete unresolved risk. At completion, review the modification scope and each acceptance criterion. Record achieved results, remaining gaps, and any lesson that affects future work in the relevant existing section. Keep delivery commentary separate from the copy-ready result. Changes to long-term memory or global rules require the user's request.

## Task Plan Template

Replace the placeholders with verified facts. Match heading language to the task plan. Add optional sections only when they contain information needed to carry out or resume the task.

    # <Task Name>

    Specification source: <actual path>.
    Working directory: <absolute path and base for relative paths>.
    Last updated: <actual timestamp with time zone>.

    ## Goal and Scope

    <User-observable outcome and acceptance criteria.>
    <Allowed changes, exclusions, existing authorization, and requested review or stopping points.>
    <Context required to understand this task.>

    ## Progress

    - [ ] <Observable milestone and its current status.>
    - [ ] <Remaining milestone or final acceptance check.>

    ## Findings and Decisions

    <Material observation or decision, evidence, reason, and effect on the approach.>
    <Unverified assumptions and what would resolve them. Write "None yet" when empty.>

    ## Implementation Steps

    <For each milestone, identify the files, dependencies, actions, and completion criteria.>
    <Include commands and expected results when they are needed to execute the step.>

    ## Verification Results

    <Acceptance item, actual command or action, actual result, and relevant evidence.>
    <Required checks that remain unverified and why. Record pending checks as pending.>

    ## Next Step

    <The exact next action, or the completed outcome and any remaining limitation.>
    <For a blocker, state what input is needed, who can supply it, and which work can continue.>
    <Include recovery instructions when interrupted work requires them.>

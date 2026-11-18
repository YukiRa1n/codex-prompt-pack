# Staged Development Prompts

Replace the placeholders with your actual task before sending. Each prompt bounds the scope of the current run. Existing authorization remains active for the task, so ordinary local edits do not need repeated confirmation. Prompts limited to investigation, planning, or verification stop at the end of that stage. Follow the global deliverable rules and keep user commentary outside the deliverable.

## Full Task

    Implement in the current project: <requirement>.
    Allowed changes: <directories or files, or "project files required to implement this requirement">.
    Out of scope: <items excluded from this run>.
    Acceptance criteria: <user-observable behavior, inputs and outputs, and required checks>.

    Read the applicable AGENTS.md or GEMINI.md, existing project plans, and relevant code first.
    Follow the global development workflow. For complex work, read the applicable PLANS.md and create or update the ExecPlan.
    I authorize the local implementation, plan updates, and verification required within this scope. Advance continuously across milestones.
    Diagnose failed checks. Within this scope, fix failures caused by the current changes and faults that block the agreed acceptance criteria. Record unrelated existing failures and their impact.
    Record actual commands, results, and unverified items. If a necessary fix exceeds scope, request a decision promptly and continue independent work.
    Investigate missing information through available evidence and authorized checks. If a critical input still determines the next action, ask promptly and pause only the dependent steps.
    Keep the deliverable free of commentary. Outside the deliverable, briefly report the file paths, line numbers, verification commands, and actual results.
    Distinguish file checks, runtime checks, and model behavior checks. State any unverified parts clearly.

## Understand the Project

    Run a read-only investigation of the current project focused on: <feature or issue>.
    Read the applicable AGENTS.md or GEMINI.md, existing plans, project docs, entry points, dependency manifests, and test configs.
    Check how the project runs, relevant call chains, existing workspace edits, available verification commands, and missing prerequisites.
    Support your conclusions with actual file paths and code locations. Distinguish verified facts from unverified hypotheses.
    State the modification scope and next step required for this requirement. Stop when the investigation finishes and do not modify files.

## Prepare Stage

    Write an executable plan for <requirement or stage>. Perform only investigation and planning in this run.
    Read the applicable AGENTS.md or GEMINI.md, PLANS.md, relevant code, and existing plans. Follow the project's existing format and path conventions.
    Allowed scope: <scope allowed for planning and writing>.
    Specify the user-observable outcome, files allowed to change, excluded scope, prerequisites, milestones, acceptance criteria, and stopping conditions.
    Confirm verification commands from the current project and mark expected outputs clearly as expected.
    For uncertain approaches, define a minimal prototype and the criteria to adopt or discard it.
    Use the plan specification's core sections and add detail only where needed. Keep Progress, Findings and Decisions, Verification Results, and Next Step current, or update equivalent existing sections. Stop after writing the plan and do not implement the feature.

## Execute a Stage

    Execute <stage or milestone> in <plan path>.
    I authorize the local implementation, plan updates, and verification required for this stage.
    Read the applicable instructions, plan, and relevant code first. Check the workspace and stage prerequisites before making edits.
    Keep changes within this stage's scope and protect existing user edits. If a necessary change exceeds scope or a critical input remains unavailable after investigation, ask promptly and continue independent work while the dependent steps wait.
    Run the checks specified in the plan and diagnose failures. Within the authorized scope, fix failures caused by this stage's changes and faults that block its acceptance criteria. Record unrelated existing failures and their impact.
    Record actual commands, working directory, exit codes, and output summaries in Verification Results. Update Progress, Findings and Decisions, and Next Step, or equivalent existing sections.
    Stop once this stage meets its acceptance criteria. Keep process notes out of the deliverable, and separately report the evidence and prerequisites for the next stage.

## Independent Verification

    Verify whether <requirement, change, or stage> meets <acceptance criteria or plan path>.
    Run checks and necessary runtime verification only. Do not modify application code.
    Check the actual diff scope and current environment first, then run the relevant checks and user-observable scenarios.
    When useful and safe, compare behavior before and after the change without overwriting existing workspace edits.
    For each acceptance item, record the command or action, actual result, exit code, evidence path, and pass or fail status.
    Distinguish file or syntax checks, runtime execution, and model behavior checks. Mark a check as passed only if you actually ran it.
    State the reason for any check that did not run. Never treat a plan, existing code, or expected output as verification evidence.
    If you find issues, report the exact locations, reproduction steps, and impact, then stop when verification finishes.

## Fix Review Findings

    Fix the confirmed issues in <review path or issue list>.
    First verify that each issue still exists in the current code, and confirm the reproduction steps, impact, and allowed modification scope.
    Apply the necessary fixes for confirmed issues and run checks that prove the fix. Where useful, show that the check fails before the fix and passes after the fix.
    For issues that lack evidence or no longer exist, record your verification findings and do not change code just to silence the report.
    Update the applicable task plan and verification evidence, then stop after fixing the authorized issues. Keep the deliverable separate from the brief verification note.

## Retrospective and Handoff

    Run a retrospective based on <task plan path>, current workspace changes, and actual verification evidence.
    Check the original goal, scope, stopping conditions, and each acceptance item. Mark completed, unfinished, and unverified items clearly.
    Record findings that affected the outcome, plan adjustments, and reasons. Do not state unverified speculation as a root cause.
    Update Verification Results with the acceptance status and evidence. Record lessons that affect future work in Findings and Decisions. Put the next action and blockers in Next Step. Include the startup method when needed to resume. Use equivalent sections in an existing plan and reference evidence already recorded there.
    Update only the task record in this run. List any suggestions for global rules, skills, or long-term memory separately without modifying those files directly.

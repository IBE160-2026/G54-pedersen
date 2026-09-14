---
title: "Product Brief: Simplified PM App"
status: final
created: 2026-09-13
updated: 2026-09-14
---

# Product Brief: Simplified PM App

## Executive Summary

Project management tools have a structural problem: they're built around concepts — epics, stories, projects, boards, workspaces — that teams have to learn, maintain, and navigate before they can do any actual work. The overhead has become the product.

We're building a web-based PM app for smaller organizations, built around a single concept: the task. No epics, no boards, no workspaces. Everything is a task, tasks nest infinitely, and there's nothing new to learn — just tasks looked at from different angles depending on what you need. The result is a tool that gets out of the way, keeps communication where it belongs, and actually feels good to use.

It's built for work teams and the project managers who lead them — people who've lived with Jira's complexity, watched context vanish into Slack, and sat through standups the tool should have made unnecessary.

---

## The Problem

A developer opens the PM tool to log progress. First: find the right project, then the right story, then the subtask — or does this work go on a separate board? Ten minutes later the work is logged and nothing is simpler.

Modern PM tools make teams maintain a vocabulary just to organize their work. The structure rarely matches how people actually think. Grooming backlogs, moving cards, keeping hierarchies tidy — that becomes the job, and the actual work is secondary.

Context leaks out. Discussions happen in Slack, decisions get made in meetings, and anyone joining later finds it hard to piece together what happened or why.

And most tools feel like filing systems. They don't reflect urgency, don't surface who's stuck, and don't create momentum. Teams end up doing the minimum to keep the board tidy, not using it to actually think.

---

## The Solution

Everything is a task. Tasks nest infinitely. That's the whole model — no structural concepts to learn or maintain.

**Task model:** Tasks have statuses, a Blocked flag, and an optional priority level. Everything you need to express what's happening with a piece of work, without inventing a new concept to do it.

**Blocking:** When a task gets blocked, the assignee is notified — including the reason, if one was written. They can reply directly to the blocking task without navigating away. The blocking task shows what it's holding up, so the person responsible sees the downstream impact without being told.

**Activity feed:** Every task has one chronological stream — comments, time logs, description edits. Mention someone anywhere on the task and they're looped in. Someone joining the project late reads the full story of any task without asking anyone.

**Visual health:** A deadline gradient turns red as the date approaches. Blocked and priority badges complete the picture. The task's health is readable at a glance, no extra dashboard needed.

**Three views — same tasks, different angles:**
- *Task tree* — the day-to-day work view for the whole team. The full task hierarchy, with done tasks hidden by default.
- *Bucket view* — a prioritization view showing tasks for a chosen status, organized by priority. Drag to reprioritize, set deadlines, without opening individual tasks.
- *Team overview* — a card for every team member showing what they're working on, whether they're blocked, how long tasks have been sitting, and hours logged. The PM can drop a comment or voice note into any task directly from the card, without leaving the view. No standup needed — the tool already knows what a standup is meant to surface.

**Voice comments:** Record audio directly on a task; it plays back in the Activity feed. Conversations stay attached to the work.

**AI-assisted editing:** Write a prompt, get a suggestion — new subtasks, a rewritten description. Nothing is applied until you say yes.

**AI daily briefing:** Each morning, a short personal note: what to focus on, what's been sitting too long, who to reach out to if something is stuck. A suggestion, not an instruction.

---

## What Makes This Different

**One concept, not five.** Most PM tools organize work through taxonomy — epics contain stories contain tasks. Here there's only the task. Complexity lives in the tree, not in the vocabulary. A task like "add button" is real, trackable work — not a bullet inside a story inside an epic.

**Blocking as a condition, not a status.** A task can be blocked before work starts or mid-progress. Blocked sits on top of any status, so the team sees what's actually happening — not an approximation of it.

**Communication that stays.** The unified Activity feed — comments, time logs, description history, voice recordings — keeps everything attached to the task that prompted it. Context is there for whoever needs it.

**AI that assists, not decides.** The AI surfaces suggestions when asked and offers a daily briefing based on real data from the feed. The team decides what to act on.

---

## Who This Serves

**Work teams** — developers, designers, and contributors tracking work, coordinating handoffs, and seeing what's blocked without navigating a multi-layer hierarchy. They're in the task tree every day.

**Project managers and leads** — responsible for team health; need to see who's stuck, what's stalled, where the blockers are. The team overview and bucket view are built for them — and accessible to everyone.

---

## Onboarding

Every new team member gets a "Get to know the system" task automatically assigned when joining the team. It comes with subtasks that walk them through the tool using real project examples. There's no separate tutorial — the product teaches itself through its own mechanic.

---

## Scope

**In:** The full task model (infinite nesting, statuses, blocking, priority levels); a unified Activity feed with comments, time logs, voice recordings, and description history; three views — task tree, bucket view, and team overview; AI-assisted task editing with user confirmation, and a daily personal briefing; a self-teaching onboarding task for every new team member. Single team, web only.

**Out (for this project):** Email notifications, recurring tasks, multi-team support, speech-to-text transcription.

---

## Success Criteria

- Teams find context for any task inside the tool — no Slack archaeology
- Blocked tasks get resolved faster because blockers and their downstream impact are visible
- Leads read team health from the overview without holding a standup
- New team members are productive within their first day
- The tool is used for real work, not just status updates

---

## Vision

A tool that grows with the team without changing its philosophy. Multi-team support is the natural next step. The AI layer deepens — smarter suggestions, pattern-based staleness detection. The one-concept philosophy holds.
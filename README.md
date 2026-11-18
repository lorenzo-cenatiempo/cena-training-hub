# Cena Training Hub

A free, interactive study program for six entry-level IT and security certifications.

**Live site:** [cenatraininghub.com](https://cenatraininghub.com)

## Why I built it

Exam vouchers are expensive, good prep courses are expensive, and a 600-page book does not help someone who struggles to sit down and study. I wanted one free place where a beginner could learn the material, practise it, and see exactly what to study next.

## What it covers

| Program | Exam |
| --- | --- |
| CompTIA Tech+ | Entry-level IT concepts |
| CompTIA A+ Core 1 | Hardware, networking and mobile devices |
| CompTIA A+ Core 2 | Operating systems, security and troubleshooting |
| CompTIA Network+ | Networking |
| CompTIA Security+ | Core security |
| Microsoft Azure Fundamentals (AZ-900) | Cloud concepts and Azure services |

## How a learner uses it

Every exam objective is taught as a short module with the same five parts:

1. **Lesson.** A plain-language explanation with a worked example, key terms and a memory aid.
2. **Quick check.** A few questions on that objective, each with an explanation written to teach.
3. **Study cards.** Key terms reviewed on a spaced-repetition schedule.
4. **Domain quizzes.** Mixed questions that test telling similar concepts apart.
5. **Practice exams.** Timed simulations scored on the real exam's scale.

A **readiness map** on the dashboard ties it together. It shows one axis per exam domain and combines accuracy with coverage, so a high score on a handful of questions does not count as mastery. Selecting a domain goes straight to the lesson or practice that will improve it.

## Features

- An exam switcher, with each program keeping its own coursework, quizzes, flashcards, simulator and progress
- Hands-on practice: port drills, subnetting and binary drills, a terminal trainer, performance-based question practice and a help-desk practicum
- Reference tools: cheat sheets, glossaries and acronym lists
- Light gamification: ocean, jungle and outer-space backdrops, a shark that comes for a missed answer, and treasure for five correct in a row
- No paywall and no sign-up needed to start learning

## How it was built

**Approach.** I built the hub with Claude, Anthropic's AI assistant, as a pair-builder. I set the scope, the structure and the features, tested each version, and directed the changes. Claude generated the code and drafted the study content against each exam's published objectives.

**Steps.**

1. **Started with one exam.** The first version was a Security+ hub: a dashboard, lessons mapped to every objective, flashcards, quizzes and an exam simulator.
2. **Separated content from code.** Lessons, questions and flashcards are stored as structured data in one shared schema, so the same application can serve any exam.
3. **Added more programs on the same chassis.** Network+ and AZ-900 used the same schema, so their content loaded as data without rewriting the app. A+ Core 1, A+ Core 2 and Tech+ followed.
4. **Built the exam switcher.** Each program has its own progress, exam date, pass mark and domain weights, so scores from one exam never blend into another's readiness.
5. **Added practice tools and the readiness map.** Drills and labs were added per exam, and every answer feeds the map.
6. **Published and gave it a real address.** The hub is a single self-contained web page (HTML, CSS and JavaScript). I registered `cenatraininghub.com` and set a permanent (301) redirect, for both the bare domain and `www`, to the published page.
7. **Tested before sharing.** I reset all saved progress to show a clean template, checked that the main sections load without errors, and confirmed the domain forwards correctly over HTTPS.

**Technical notes.**

- Single-page application in one HTML file, with no build step and no server
- Progress is saved in the visitor's own browser, separately for each exam
- Two optional tutoring features and cross-device progress sync need the visitor to sign in to Claude; everything else works without an account

## What I learned

- Designing a data schema first made adding five more exams far cheaper than building the first one.
- Keeping each exam's progress separate matters. Blended scores would have made the readiness map misleading.
- Domain forwarding is a quick way to give a project a professional address, with a trade-off: the browser shows the host's address after the redirect.
- Working with an AI assistant still needs a clear specification and careful testing. The quality came from reviewing each version and asking for specific changes.

## Limitations and next steps

- The content is study material I produced for learners. It is not affiliated with or endorsed by CompTIA or Microsoft, and exam objectives change, so always check the official objectives.
- The custom domain forwards to the hosted page; it is not yet hosted on its own domain.
- Planned: more certifications, and hosting under the custom domain.

## Feedback

Suggestions and corrections are welcome. Open an issue in this repository.

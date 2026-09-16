This is where my notes regarding Git and GitHub are organized.

Me : Help me learn how to use GitHub and Projects in GitHub. I want to improve my productivity and complete many projects.

ChatGPT : GitHub can work well as a **project execution system**, not merely a place to store code. For your goal—learning while actually finishing many projects—I’d teach it as a workflow.

### The system I recommend

**GitHub**

* **Repository** → one substantial project
* **README** → what the project is and how to use it
* **Issues** → individual pieces of work/problems
* **Labels** → categorize work (`bug`, `feature`, `learning`, `documentation`)
* **Milestones** → meaningful project checkpoints
* **Projects** → your visual project-management dashboard
* **Branches** → isolated work
* **Pull Requests** → review/integration mechanism
* **Commits** → small records of completed changes

### Your workflow

**Idea → Project → Issues → Board → Branch → Code → Commit → PR → Done**

For example:

> Build a URL shortener
> → create repository
> → create 10–20 issues
> → organize them in a GitHub Project
> → take one issue
> → create branch
> → implement
> → commit
> → PR
> → close issue
> → move to next issue

I can teach this **hands-on**, starting from absolute zero and gradually building a real project-management system.

Me : > What is your Git/GitHub experience?
Complete beginner

> What do you want GitHub Projects to manage?
All of these

ChatGPT : We’ll start from zero and build one system that handles **learning, personal development, career work, and coding projects** without turning GitHub into an unnecessarily complicated task manager.

### Lesson 1: Understand the mental model

Think of GitHub as three connected layers:

**1. Repository = the project’s home**
Contains the actual work: code, notes, documentation, etc.

**2. Issues = units of work**
Examples:

* “Learn HTTP basics”
* “Implement login”
* “Fix database connection”
* “Write project README”

**3. GitHub Project = your control panel**
It shows and organizes issues across repositories. This is where you can see **Backlog → Doing → Done**, priorities, deadlines, grouping, and progress.

For your use case, I recommend:

> **Pursuit → Milestone → Initiative → Repository/Project → Issue → Task**

But we should learn GitHub itself first rather than immediately reproducing your entire planning hierarchy.

### Your first exercise

Create a GitHub account/repository only if you don't already have one. Then tell me:

**“I’m ready for Lesson 2.”**

I’ll teach you Git vs GitHub, repositories, commits, branches, issues, and Projects in that order, using one small practice project throughout.

Me : I have created the GitHub Account and I am ready for the second lesson

ChatGPT : ## Lesson 2 — Git, GitHub, and your first repository

Before using GitHub Projects, you need three concepts clearly separated:

**Git** = version control software on your computer.
It records changes to your files over time.

**GitHub** = an online platform that hosts Git repositories and adds collaboration/project-management features.

**Repository (repo)** = the complete workspace for a project: files + Git history + GitHub features such as Issues and Pull Requests.

### Your first Git workflow

You will eventually use:

**Edit files → `git add` → `git commit` → `git push` → GitHub**

Think of a **commit** as a saved checkpoint with an explanation:

> “Implemented basic calculator”

A **push** sends those commits from your computer to GitHub.

---

### Exercise: create your first repository

On GitHub:

1. Click **+ → New repository**
2. Name it: `github-learning`
3. Add a description: `Learning Git and GitHub`
4. Choose **Public**
5. Select **Add a README file**
6. Create the repository

Do **not** worry about branches, Issues, or Projects yet.

Once you've created it, tell me **“Repository created.”** Then we'll connect it to Git on your computer and make your first commit.

Me : Created the Repository

ChatGPT : ## Lesson 3 — Connect Git to GitHub

Now we’ll make the same repository usable from your computer.

### 1. Install Git

Download Git from the official site:

[https://git-scm.com/downloads](https://git-scm.com/downloads)

During installation, the default options are fine.

### 2. Open Git Bash

After installation, open **Git Bash**.

Run:

```bash
git --version
```

You should see something similar to:

```text
git version 2.x.x
```

### 3. Configure your identity

Use the name you want associated with your commits:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Use the email associated with your GitHub account.

### 4. Clone your repository

On your GitHub repository page, click **Code → HTTPS**, copy the URL, then run:

```bash
git clone YOUR_REPOSITORY_URL
cd github-learning
```

You now have a local copy of your GitHub repository.

Run:

```bash
git status
```

This command is extremely important. It tells you what Git currently sees in your project.

Run those steps and tell me what `git status` shows.

Me : I actually have 2 accounts right now one is the current email one and another one is a official one for work showcase and stuff if I want to use two of them interchangeably what should i do?

ChatGPT : Yes. It is common to use **two GitHub accounts**, and you can switch between them cleanly. The important distinction is:

* **GitHub account** → determines where the repository lives and who owns it.
* **Git identity** → name/email attached to commits.
* **Authentication** → determines which GitHub account your computer is acting as.

For your situation, I recommend:

**Personal/current account**
→ learning, experiments, private projects, unfinished work.

**Professional/showcase account**
→ polished projects, portfolio, open-source contributions, career-facing work.

You can keep both accounts on the same computer. The cleanest setup is usually **SSH with separate SSH keys**, so Git automatically knows which account to use based on the repository.

For example:

```text
github-personal
github-work
```

Then repositories can be configured so pushing to each one uses the appropriate account.

**Do not configure anything further yet.** Since we're learning from zero, I suggest we first understand how Git authentication works, then set up your two-account configuration correctly rather than potentially creating confusing credentials.

Next lesson: **Git identity vs GitHub authentication**, followed by setting up both accounts safely.

Me : S:\Personal Projects\github-learning>git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

ChatGPT : Good. That output means your local repository is correctly connected to GitHub.

You currently have:

```text
main
```

as your active branch, and:

```text
origin/main
```

as the corresponding branch on GitHub.

Most importantly:

```text
nothing to commit, working tree clean
```

means Git sees no changes that haven't been saved as commits.

### One important correction

Because you have **two GitHub accounts**, we should configure authentication **before you start pushing meaningful work**. Your current repository may already be authenticated through HTTPS, potentially using whichever account Windows/Git credential storage selected.

For learning, let's first examine what identity and remote you're using.

Run these three commands:

```bash
git config --global user.name
git config --global user.email
git remote -v
```

Paste the output here. **Don't paste passwords or access tokens.**

Me : S:\Personal Projects\github-learning>git config --global user.name
project-atlas-26

S:\Personal Projects\github-learning>git config --global user.email
project.atlas.29.7.2026@gmail.com

S:\Personal Projects\github-learning>git remote -v
origin  https://github.com/project-atlas-26/github-learning.git (fetch)
origin  https://github.com/project-atlas-26/github-learning.git (push)

S:\Personal Projects\github-learning>

ChatGPT : Your configuration is currently:

```text
Git identity:
Name:  project-atlas-26
Email: project.atlas.29.7.2026@gmail.com

Remote:
https://github.com/project-atlas-26/github-learning.git
```

That means your **commits will be attributed to that name/email**, and this repository points to the `project-atlas-26` GitHub account.

One important distinction:

**`git config user.email` does not choose which GitHub account you authenticate as.** It controls commit authorship. Your HTTPS credentials determine which GitHub account actually has permission to push.

Since you want two accounts, we should avoid casually changing the global configuration. A better setup is:

```text
Personal repositories → personal Git identity + authentication
Professional repositories → professional Git identity + authentication
```

We can configure this **per repository**, allowing you to use both accounts without repeatedly changing global settings.

### Next

Before changing anything, run:

```bash
git config --local --list
```

Paste the output. This will teach you an important Git concept: **global configuration vs repository-specific configuration**.

Me : S:\Personal Projects\github-learning>git config --local --list
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.symlinks=false
core.ignorecase=true
remote.origin.url=https://github.com/project-atlas-26/github-learning.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.main.remote=origin
branch.main.merge=refs/heads/main

ChatGPT : That output is exactly what we expected.

### What you just discovered

Git has **three useful configuration levels**:

| Level      | Applies to        |
| ---------- | ----------------- |
| `--system` | Entire computer   |
| `--global` | Your Windows user |
| `--local`  | One repository    |

Your repository currently has **no local `user.name` or `user.email`**. Therefore, Git falls back to your global settings:

```text
global name  → project-atlas-26
global email → project.atlas.29.7.2026@gmail.com
```

This becomes important with your two-account setup.

### Recommended arrangement

We can eventually have:

```text
Personal repo
→ local Git identity = personal account

Professional repo
→ local Git identity = professional account
```

while leaving your global identity as a sensible default.

Your `github-learning` repository is already correctly configured as a personal repository.

### One thing we should fix conceptually

Your current remote is:

```text
https://github.com/project-atlas-26/github-learning.git
```

That's **HTTPS authentication**. With two GitHub accounts, SSH is generally the cleaner setup because each account can have its own SSH key.

We will learn that shortly.

For now, don't change anything in this repository.

**Next lesson: making your first actual change, commit, and push.** That will give you the fundamental Git cycle before we introduce SSH and the two-account configuration.

Me : Okay

ChatGPT : ## Lesson 4 — Your first Git cycle

We’ll now make a harmless change to your `github-learning` repository.

### 1. Create a file

Inside:

```text
S:\Personal Projects\github-learning
```

create a file named:

```text
notes.txt
```

Put this inside:

```text
I am learning Git and GitHub.
```

### 2. Check Git

Run:

```bash
git status
```

You should see `notes.txt` under **Untracked files**.

### 3. Stage it

```bash
git add notes.txt
```

Then:

```bash
git status
```

Now it should appear under **Changes to be committed**.

### 4. Commit it

```bash
git commit -m "Add Git learning notes"
```

A commit is a permanent checkpoint in Git's history.

### 5. Push it to GitHub

```bash
git push
```

Then refresh your GitHub repository. You should see `notes.txt`.

Run these steps in order. Paste the output of `git status` **after `git add notes.txt`**, before committing.

Me : S:\Personal Projects\github-learning>git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        notes.txt

nothing added to commit but untracked files present (use "git add" to track)

S:\Personal Projects\github-learning>git add notes.txt

S:\Personal Projects\github-learning>git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   notes.txt


S:\Personal Projects\github-learning>git commit -m "Add Git learning notes"
[main 81c4d48] Add Git learning notes
 1 file changed, 1 insertion(+)
 create mode 100644 notes.txt

S:\Personal Projects\github-learning>git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 16 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 353 bytes | 176.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/project-atlas-26/github-learning.git
   2f1d8db..81c4d48  main -> main

ChatGPT : You completed the full Git cycle successfully:

**Working file → Untracked → Staged → Committed → Pushed**

Your commit:

```text
81c4d48  Add Git learning notes
```

is now on GitHub.

### What each command actually did

```bash
git status
```

Asked Git: **“What has changed?”**

```bash
git add notes.txt
```

Told Git: **“Include this change in my next commit.”**

```bash
git commit -m "Add Git learning notes"
```

Created a **checkpoint in Git history**.

```bash
git push
```

Uploaded that checkpoint to GitHub.

This four-command cycle is fundamental:

> **status → add → commit → push**

### Next: GitHub Projects

Now we can start addressing your actual productivity goal.

We'll create a **GitHub Project that acts as your project dashboard**, then learn:

**Issues → fields → views → Board → workflows → milestones**

We'll use your `github-learning` repository as the practice environment rather than creating another project unnecessarily.

Me : Okay. I am ready

ChatGPT : ## Lesson 5 — GitHub Projects

Now we move from **version control** to **project management**.

For your productivity system, think of a GitHub Project as a **dynamic dashboard of work items**, while the repository contains the actual project files.

### Step 1: Create your Project

On GitHub:

1. Click your profile picture → **Your projects**
2. Click **New project**
3. Choose **Board**
4. Name it:
   **GitHub Learning**
5. Create it.

You should get columns similar to:

**Todo | In Progress | Done**

### Step 2: Understand the relationship

Your structure is:

```text
GitHub Project
    ↓
Issues
    ↓
Actual work
    ↓
Repository
```

An **Issue** is essentially a trackable piece of work.

For example:

```text
Issue #1 — Learn Git branches
Issue #2 — Learn GitHub Issues
Issue #3 — Learn GitHub Projects
```

The Project can then display these Issues as cards and let you move them through your workflow.

### Your exercise

Create your Project first.

Then tell me what columns/views GitHub created automatically. We’ll create your first Issue and connect it to the Project.

Me : Created the Project and the issues you showed here

ChatGPT : Good. You now have the basic GitHub Projects structure.

## Lesson 6 — Issues vs. Project items

There is an important distinction:

**Issue:** the actual unit of work.
**Project:** the system that organizes and tracks that work.

For example:

```text
Issue #1: Learn Git branches
Issue #2: Learn GitHub Issues
Issue #3: Learn GitHub Projects
```

Your Project should display those Issues as cards.

### Try this

Open your **GitHub Learning** Project.

For each Issue, set:

**Status**

* Todo
* In Progress
* Done

Then move:

```text
Learn Git branches → In Progress
```

Leave the others in **Todo**.

Now you've created your first workflow:

```text
Todo → In Progress → Done
```

### One important principle

Don't make every tiny action an Issue.

Good Issue:

> **Build a CLI habit tracker**

Poor Issues:

> Open VS Code
> Create folder
> Type first line

The Issue should represent a **meaningful outcome**, while the smaller steps can live inside it as a checklist.

Next we'll learn **labels, priorities, and custom fields**, which are what make Projects useful for managing many projects simultaneously.

Me : Dude you are going on a tangent there

ChatGPT : You're right. I was moving ahead of the learning sequence instead of teaching the specific thing you had just reached.

Let's reset.

You have:

* GitHub account
* Repository
* Git installed
* Repository cloned locally
* Made and pushed your first commit
* GitHub Project created
* Three Issues created

From here, I'll teach **one concept at a time**, with a short explanation and a concrete exercise. No jumping ahead.

### Lesson 6: What exactly is a GitHub Project?

Before changing fields or workflows, you should understand the basic architecture:

**Repository** stores your project/files.
**Issue** describes a piece of work.
**Project** organizes Issues (and other items) into a view for planning/tracking.

That's it for this lesson.

Open your Project and click one of the Issues you created. Tell me **what you see on the Issue page**. Then we'll learn exactly how an Issue connects to a Project.

Me : The Issue page shows. History of the issue. assignee, labels, projects, milestones, relationships, development notifications, participants. and comments

ChatGPT : Exactly. That page is showing the **metadata and relationships around an Issue**. For now, focus on these three:

* **Assignee** → who is responsible for the work.
* **Labels** → what kind of work it is.
* **Projects** → which GitHub Project is tracking it.

The others can wait.

### The key concept: Issue ↔ Project

Your Issue can exist independently:

> **Issue #1 — Learn Git branches**

Then the **Projects** section associates that Issue with your **GitHub Learning** Project.

Once associated, the Issue becomes an item/card inside that Project. Changes made in the Project and changes made on the Issue refer to the same underlying work item.

### Exercise

On this Issue, find **Projects** and make sure **GitHub Learning** is selected.

Then open your GitHub Learning Project and confirm that **Issue #1** appears there.

Once you've confirmed that, we'll examine exactly **what the Project is adding beyond the Issue itself**.

Me : I already see it. since we have created the issue from the todo part of the project view. it also shows in progress in the view as well as the issue page inside the project "subtopic?"

ChatGPT : Yes. That is the important observation.

What happened is:

**Project → Todo → Create Issue**

GitHub created the Issue **and added it to the Project simultaneously**. The Issue therefore has a corresponding item in the Project.

Also, **“In Progress” is a Status field on the Project item**, not a separate state of the Issue itself.

So conceptually:

```text
Issue
  ↕
Project item
```

They represent the same piece of work, but GitHub gives you two interfaces for interacting with it.

One correction: the section you're calling a “subtopic” is probably the **Project association/context shown on the Issue page**, rather than a hierarchy underneath the Issue.

Next, let's answer one specific question:

**Why would you use a GitHub Project when Issues already exist?**

That distinction is the foundation for understanding Projects.

Me : duh to organize multiple repositories' issues and prioritize them for efficiency

ChatGPT : Correct. That is the core reason.

An **Issue answers:** “What needs to be done?”

A **Project answers:** “What should I work on, across everything I’m doing, and in what order?”

For your use case:

```text
Repository A
 ├─ Issue 1
 └─ Issue 2

Repository B
 ├─ Issue 3
 └─ Issue 4
          ↓
   GitHub Project
   ├─ Todo
   ├─ In Progress
   └─ Done
```

So Projects become your **cross-project execution layer**, while repositories remain the homes of individual projects.

And yes, **prioritization** is one of the major reasons to use Projects.

You already understand the fundamental purpose, so there's no reason to spend another lesson explaining it. Next we should learn the **Project fields that let you actually prioritize and filter this work**.

Me : sure go on

ChatGPT : ## Lesson 7 — Project fields

A Project becomes useful when you attach **information to each work item** beyond just its status.

Start with one field: **Priority**.

In your GitHub Project:

1. Click the **+** beside the existing fields/columns.
2. Add a **Single select** field.
3. Name it **Priority**.
4. Create values:

   * `P0 — Critical`
   * `P1 — High`
   * `P2 — Normal`
   * `P3 — Low`

Now each Issue in your Project can have a priority independently of its repository.

For your three Issues, assign priorities arbitrarily for practice.

The important distinction:

**Status = where the work is.**
**Priority = how important the work is.**

Don't add any other fields yet. Once you've created Priority and assigned it to the three Issues, we'll learn **how to sort and filter the Project using it**.

Me : dude be clear which plus are you talking about the column one the view one or the attribute/ field

ChatGPT : The **attribute/field +**, not a column/card +.

In your GitHub Project table view, there are usually several `+` controls that can look similar:

* **Column/Status area:** adds another view column/group.
* **Item/card area:** adds a new issue/project item.
* **Field/attribute area:** adds a Project field such as Priority.

For the exercise, use the **`+` associated with the existing fields/attributes**—the area containing things like **Status, Assignees, Labels, Projects**.

Then choose **New field → Single select → Priority**.

If your interface looks different, send me a screenshot of the Project page and I’ll point to the exact control.

Me : so View settings and under fields right?

ChatGPT : Yes. **View settings → Fields**.

That is where you control which fields/attributes are displayed in that view.

However, one distinction: **Fields** there controls the fields shown; it may not be where you create a new custom field. To create **Priority**, use the Project's **field-management option** (often `+` beside the fields or **Add field → New field**), depending on the current GitHub UI.

If you show me a screenshot of your Project's **View settings → Fields** area, I can identify the exact control.

Me : 	I see only 5 + symbols

1. on hover says to create a new repo/project/codespace, etc....
2. beside the view 1 tab, to create a new view under this project.
3. beside the columns, to add a new column.
4. beside the column heading, add item to the specific column.
5. Inside the column which shows add item

ChatGPT : Yes—your screenshot makes the situation clear, and my earlier direction was wrong.

You are currently using a **Board view**. In this view, those five `+` buttons are not for creating custom fields.

To create a custom **Priority** field, GitHub’s current UI requires a **Table view**. GitHub documents custom-field creation from the rightmost field header in a table view. ([GitHub Docs][1])

### Do this

At the top, click:

**`+ New view` → choose `Table`**

Call it:

**Table**

Once the Table view opens, you'll see fields such as **Title, Status, Assignees, Labels**, etc., with a `+` at the right end of the field headers.

**That `+` is the one I meant.**

Don't change anything else yet. Create the Table view and tell me when you're looking at it.

[1]: https://docs.github.com/en/issues/planning-and-tracking-with-projects/understanding-fields/about-text-and-number-fields?utm_source=chatgpt.com "About text and number fields - GitHub Docs"

Me : now in the table view I see;

- title
- asignee
- status
- linked pull requests
- sub-issues progress
- plus symbol

ChatGPT : Exactly. **That final `+` after “Sub-issues progress” is the correct one.**

Click that `+`.

You should get an option to **add a field**. Choose:

**New field → Single select**

Set:

**Field name:** `Priority`

**Options:**

* `P0 — Critical`
* `P1 — High`
* `P2 — Normal`
* `P3 — Low`

That creates a **custom Project field**. It is separate from GitHub's built-in fields like Status, Assignee, and Labels.

For now, just create the field. Don't worry about assigning priorities yet.

Me : Yes. The screenshot resolves it.

I gave you the wrong instruction earlier: the `+` opened **Add issue fields**, not the custom Project-field creator.

In your dialog, click:

**`Create a project field`**

Then create:

**Name:** `Priority`
**Type:** `Single select`

Options:

```text
P0 — Critical
P1 — High
P2 — Normal
P3 — Low
```

This is the field we want.

The distinction is:

**Issue field** → information defined for Issues and reusable across Projects.
**Project field** → information specific to this Project.

For our productivity system, we want **Project fields**.

Click **Create a project field**, and tell me what appears next.

Me : there is now a subsection in the add a field drop down "project fields" under that we have the one we want

ChatGPT : Correct. **That is the one we want.**

Select the **Priority** field under **Project fields**.

You don't need to create another field now—the field has already been created; you're simply **adding it to this view**.

Once selected, your Table should show something like:

`Title | Assignee | Status | Linked PRs | Sub-issues progress | Priority`

Then assign different priorities to your three Issues.

For example:

```text
Learn Git branches    → P1 — High
Learn GitHub Issues   → P2 — Normal
Learn GitHub Projects → P1 — High
```

The specific choices don't matter yet. We're learning how the field works.

Me : Done

ChatGPT : Good.

### Lesson 8 — Sorting by Priority

Now you have **Priority**, but a field is only useful if you can use it to change how you see your work.

In your **Table view**:

1. Open **View**.
2. Find **Sort**.
3. Add a sort by **Priority**.
4. Choose descending/ascending so your highest-priority items appear first.

You should then be able to look at your project and immediately see:

> **What should I work on first?**

This is the beginning of turning GitHub Projects into an actual execution system rather than just a list of Issues.

Do that with your `Priority` field. Then we'll learn **filters**, which let you create views like “only high-priority unfinished work.”

Me : done now the issues are arranged in descending order based on the priority selected

ChatGPT : Exactly. You now have the basic **prioritization mechanism** working.

One important detail: GitHub's sorting is based on the field's defined option order, so your `P0 → P3` ordering gives the Project a predictable priority hierarchy.

### Lesson 9 — Filtering

Sorting answers:

> “Show everything, but put the important work first.”

Filtering answers:

> “Show me only the work I care about right now.”

In the Table view:

**View → Filter**

Then filter by:

**Priority → P1 — High**

Your table should now display only the high-priority Issues.

After that, remove the filter and try:

**Status → In Progress**

This is the basis for creating specialized views later, such as:

> **Current Work** = In Progress + P0/P1

Do those two filters manually. We won't create another view yet.

Me : done I checked out the priority filter that showed the issue 1 and 3 for high priority. Then showed issue 1 alone for status 'in progress'

ChatGPT : Correct. You have now demonstrated both:

**Filter by Priority**
→ Issues #1 and #3 (`P1 — High`)

**Filter by Status**
→ Issue #1 (`In Progress`)

So you understand the difference:

> **Sort = change the order of items.**
> **Filter = change which items are visible.**

### Lesson 10 — Why Views exist

Rather than repeatedly applying filters manually, GitHub lets you **save different configurations as separate views**.

For example, one Project could eventually have:

**Board — Execution**

> Todo → In Progress → Done

**Table — Priorities**

> Everything sorted by Priority

**Table — Current Work**

> Only In Progress items

Each view uses the **same underlying Issues/project items**. You're not duplicating work.

For the next step, create a second view called **Current Work**. We'll configure it together rather than adding anything else yet.

Me : Okay go on

ChatGPT : ## Lesson 10 — Create your first useful view

Create a new view:

**`+` beside your existing view tab → Table**

Name it:

**Current Work**

Then configure it:

**Filter → Status → In Progress**

Now this view should show only Issue #1, because that's currently the only issue you marked In Progress.

The important concept is that **the view saves the configuration**, not a separate copy of your Issues.

So:

```text
Issue #1
Status: In Progress
Priority: P1
        ↓
Current Work view
        ↓
Visible
```

Change Issue #1 back to **Todo** afterward. Watch what happens to the Current Work view.

This demonstrates why saved views are powerful.

Me : When I moved issue #1 back to todo it vanished from the current work view

ChatGPT : Exactly. That is the intended behavior.

Your **Current Work** view is essentially a live query:

```text
Show me items where:
Status = In Progress
```

When Issue #1 changed to **Todo**, it no longer satisfied the condition, so GitHub removed it from that view automatically.

This gives you a powerful mental model:

> **Issues are the data. Views are saved ways of looking at that data.**

You can therefore have one set of Issues but many useful views without duplicating anything.

### Next: the Board view

Now let's return to your original **Board** view and connect what you've learned:

**Status** determines which column an item appears in.

So when you move an Issue:

`Todo → In Progress`

you're actually changing its **Status field**, and the Board rearranges it automatically.

Set Issue #1 back to **In Progress** and observe the Board.

Me : done. it moved from the todo pile to the in progress pile

ChatGPT : Exactly. You’ve now seen the mechanism firsthand:

```text
Issue status changes
        ↓
Project item changes
        ↓
Board position changes
        ↓
Filtered views update automatically
```

That is the foundation of GitHub Projects.

### Lesson 11 — Labels vs Priority

There is an important distinction before we build a larger system:

**Priority** answers:

> How important is this?

**Label** answers:

> What kind of work is this?

For example:

```text
Issue: Implement authentication

Priority: P1 — High
Labels: feature, security
Status: In Progress
```

One Issue can have multiple labels but one Priority.

Let's add **two labels** to your Issues:

`learning`
`git`

Use them just for practice. Then we'll learn how labels can be used alongside filters.

Me : Okay

ChatGPT : ### Lesson 11 — Add labels

For practice, add these two labels to your Issues:

* `learning`
* `git`

GitHub labels describe the **category or nature of the work**, while Priority describes its **importance**.

For example:

```text
Issue #1: Learn Git branches
Status:   In Progress
Priority: P1 — High
Labels:   learning, git
```

You can add labels from the **Labels** section on the Issue page.

Assign:

* `learning` to all three Issues
* `git` to the Git-related Issues

Once done, we'll use **labels as another filter**, which will show why having both Priority and Labels is useful.

Me : Added the labels as well.

ChatGPT : ### Lesson 12 — Combine filters

Now use the labels you created.

In your **Current Work** view:

**View → Filter → Labels → `git`**

You should see only Issues carrying the `git` label.

Then try combining filters:

```text
Status = In Progress
AND
Label = git
```

This is where GitHub Projects becomes genuinely useful: you can answer questions like:

> “Which Git-related work am I actively doing?”

rather than manually scanning every Issue.

After trying that, we’ll move to **Milestones**, which is especially relevant to the planning hierarchy you want to build.

Me : Okay done. for now forget about me.

ChatGPT : Understood. I’ll treat this as a **generic GitHub/GitHub Projects course**, not tailor the next lessons around your personal planning system.

Next we’ll cover the GitHub fundamentals in a clean progression:

**Issues → Milestones → Projects → Branches → Pull Requests → Releases → collaboration workflows**

We’ll keep the examples generic and focus on understanding how GitHub itself works.
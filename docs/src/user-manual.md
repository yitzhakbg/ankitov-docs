# AnkiTov User Manual

This manual is written for the people who *use* AnkiTov — teachers and
students — not for developers. For architecture, development, and operations
details, see the [Architecture](architecture.md) and
[Development](development/getting-started.md) sections.

> **Where is the console?**
> The Management Console is a web app served by the AnkiTov backend:
>
> - **`/dashboard/`** — the main console (called the **IMP Console**). This is
>   what you will use 99% of the time.
> - **`/imp-console`** — the same console, alternate route.
>
> Both are multilingual (English, Arabic, Hebrew, Hindi, Japanese, Korean,
> Chinese, German, Spanish, French, Italian, Portuguese, Russian). Pick your
> language in the top bar; the console remembers your choice.

---

## 1. Roles

| Role | Who | What they can do |
|------|-----|------------------|
| **Admin / Operator** | Your school's IT or platform lead | Enroll teachers, configure the system, manage all classes and students |
| **Teacher** | The instructor running a class | Upload decks, create classes, set practice plans, generate sessions, view progress |
| **Student** | A learner in a class | Complete assigned practice sessions, see their own progress |

You arrive in the console as one of these three. Most of this manual is about
the **teacher** view; the student experience is mostly "get your cards, review
them, done."

### Getting your first login

1. Your school's admin **enrolls you** (see [§3 Teachers](#3-teachers) —
   this is an admin-only action).
2. You receive an **invite** — a link or printed handoff.
3. Open the link → you land on the **First Login** wizard, where you
   **set a password**, **confirm your language**, and **consent to the
   privacy policy**.
4. You are logged straight in.

From then on you log in normally (email/password) and the system remembers you.

---

## 2. The Console at a Glance

The sidebar is your map. It splits into two groups:

- **Classroom** — the day-to-day: `🏠 Home`, `🧠 Study Session`,
  `📈 Class Insights`, `✅ Progress Tracker`.
- **Setup** (collapsed by default) — where configuration lives:
  `📚 Classes`, `📦 Decks`, `🏷️ Tracks & Profiles`,
  `🧑‍🏫 Teachers` (admin only), `🔄 Sync`.

Plus a **❓ Help** button that opens the in-app **Help Center** — a
searchable set of articles that covers everything in this manual (and more).
*If you ever get stuck, the Help button is your friend.*

The top bar shows your current **class/profile switcher**, a global search
box, and a **system health** badge (green = all good).

### 2.1 First-Run Wizard

The first time you open **Home** as a teacher, a **three-step wizard** pops up
to get you running:

1. **Create your first class** — name, subject, period (e.g. *7th Grade
   Science / Period 3*).
2. **Add students** — paste a list of names, or import from a
   `.csv` / `.tsv` / `.txt` file.
3. **Assign decks** — pick which uploaded decks this class uses (or skip and
   do it later).

You can **Skip setup** at any point; the wizard re-appears on Home until you
finish it, so you're never locked out.

---

## 3. Teachers

*(This screen is visible to admin/operator roles only.)*

The **Teachers** screen is how an admin **enrolls a new teacher**:

1. Click **＋ New Teacher**.
2. Fill in name, email, and the institutional fields (school/community,
   role/class, preferred language).
3. The system creates the account **without a password** and generates an
   **invite token**.
4. Send the teacher the **invite link** (by email or print it out).

The teacher then goes through the [First Login wizard](#1-roles) to set their
own password — the admin never needs to know it.

You can also check **invite status** here: which invites are still
unclaimed, which have been activated, and who the teacher is once active.

---

## 4. Classes

**Classes** group students so you can manage them, filter reports, and assign
decks/plans in one action.

- **Create**: **＋ Create a Class** → name, subject, period.
- **Add students**: paste names or import a file (same as the wizard step 2).
- **Assign**: distribute decks and practice plans to the whole class at once.

Once a class exists, you can filter **Home**, **Class Insights**, and the
**Progress Tracker** to that class for a per-group view.

> **💡 Tip:** One class = one teaching group (e.g. one homeroom, one period).
> Don't try to put your whole school in one class — make one per group.

---

## 5. Decks

A **deck** is a collection of flashcards. In AnkiTov, decks are the raw
material students practice from.

- **Upload**: **＋ Upload** or drag-drop an **`.apkg`** file onto the Decks
  screen. (An `.apkg` is a standard Anki shared deck — you can make/export
  them in the regular Anki app.)
- **Distribute**: click **Distribute** on a deck to send it to a class or
  individual students.

> **Why `.apkg`?** It's the native Anki format, so anything you already have
> in Anki works without conversion.

---

## 6. Tracks & Profiles

*(Also labeled **Modules & Practice Plans** in some places — same thing, two
names.)*

This is the heart of how AnkiTov decides *what* a student reviews. Two
concepts:

### Modules (aka **Tracks**)
A **module** is a **topic area** — a collection of related flashcards, like
*"Fractions"*, *"Vocabulary"*, or *"Cell Biology"*. A module is the smallest
meaningful unit of curriculum.

### Practice Plans (aka **Profiles**)
A **practice plan** combines **one or more modules** plus a **weekly session
target** (how many practice sessions per week, 1–7). A plan is then
**assigned to a student** and tells AnkiTov which topics to cover and how
often to review.

**To create a plan:**

1. Go to **Setup → Practice Plans**.
2. Click **＋ New Plan**.
3. Choose which modules to include.
4. Set **Weekly Sessions** (most teachers use **3**).
5. Assign the plan to students.

> **💡 Tip:** Start with **3 weekly sessions** per student. You can dial it up
> or down later based on their progress data.

> **FAQ — can a student have two plans?** No. Each student has **one active
> plan at a time**; assigning a new plan replaces the old one.

---

## 7. Study Session

A **practice session** is a personalized set of review cards for **one
student** to complete **in one sitting**. The system picks the cards the
student is *due* to review, based on their practice plan and the scheduling
algorithm (see the [Glossary](#glossary) for how smart scheduling works).

**To generate one:**

1. Go to **Classroom → Study Session**.
2. Pick a student (or several).
3. Choose their practice plan.
4. Set a session duration if needed.
5. Click **Generate**.

The result is a ready-to-review set you can print, screen-share, or hand to
the student — exactly the cards they need right now, nothing more.

> **💡 Tip:** This is your "daily driver." If you only do two things each day,
> make one of them **generate today's sessions** for your at-risk students.

---

## 8. Class Insights

**Class Insights** shows **class-wide trends**: retention curves, common
problem areas, and practice patterns across the group.

- Use the **dropdown** to select a class.
- Look for **topics where the whole class is struggling** — that's where a
  re-teach pays off.

This is your "how is the group doing?" dashboard. Individual per-student
numbers live in the [Progress Tracker](#9-progress-tracker-compliance).

---

## 9. Progress Tracker (Compliance)

The **Progress Tracker** shows, per student, **how consistently they are
completing their assigned practice sessions** over time.

**Color codes:**

| Color | Range | Meaning |
|-------|-------|---------|
| 🟢 **Green** | 80–100% | On track — keep it up! |
| 🟡 **Yellow** | 50–79% | Slightly behind — may need a nudge |
| 🔴 **Red** | below 50% | **At risk** — needs attention |

> **"At-risk"** = a student who **missed 2+ sessions this week**.

**How to use it:** scan for red/yellow students, then jump to
[Study Session](#7-study-session) to generate a make-up or catch-up session.
This is the screen that turns "I *think* they're behind" into "here is the
data."

---

## 10. Sync

The **Sync** screen shows whether each student's practice data is
**synchronized** with the server.

- 🟢 **Green** = up to date.
- 🔴 **Red** = sync is needed or has failed.

Click **Trigger Full Sync** to force-sync **all** students at once. Use this
after bulk changes (new decks, new plans) or when a student reports they
"aren't seeing the right cards."

> **Troubleshooting:** If a single student is stuck on red, try a full sync,
> then re-generate one of their sessions. If it persists, it's a data issue
> — open an issue and attach their student ID.

---

## 11. Help Center & Glossary

The **❓ Help** button opens the in-app **Help Center**: a searchable set of
articles covering every concept in this manual. It's the fastest way to
find the answer when you're mid-class.

### Glossary

| Term | Meaning |
|------|---------|
| **Module / Track** | A topic area, e.g. "Fractions" or "Vocabulary" |
| **Practice Plan / Profile** | A set of modules + a weekly session target, assigned to a student |
| **Practice Session** | A personalized review set for one student, one sitting |
| **Weekly Sessions** | How many practice sessions per week (1–7) |
| **Progress** | How consistently a student is completing their sessions |
| **Smart Scheduling** | The system picks the optimal time to review each card |
| **Retention** | Percent of cards remembered correctly |
| **At-Risk** | Students who missed 2+ sessions this week |
| **Deck** | A collection of flashcards (an `.apkg`) |
| **Class** | A group of students, filtered across Home/Insights/Progress |

---

## 12. Troubleshooting

| Symptom | First move |
|---------|-----------|
| "I can't log in" | Confirm you used your *own* password (the one you set at first login), not the invite token. Still stuck → contact admin; your password may need reset. |
| "My students aren't showing" | Re-import the CSV in **Classes** (step 2 of the wizard). Check the file is names-only, one per line. |
| "Deck won't upload" | It must be a valid **`.apkg`** (Anki shared deck), not a loose CSV or ZIP. Export from Anki if unsure. |
| "Session generated the wrong cards" | Check the student's **active plan** (Tracks & Profiles) — it controls which modules are due. Assign the correct plan, then regenerate. |
| "Student data looks stale" | **Sync → Trigger Full Sync** (§10). |
| "Something is red/broken" | Check the **system health** badge in the top bar and the **Sync** screen. If red, open an issue with the badge text and your timestamp. |

> **Still stuck?** Open an issue with: the screen you're on, a screenshot,
> the student(s) affected, and what you *expected* to happen vs. what you saw.

---

## 13. Frequently Asked Questions

**What's the difference between a Module and a Practice Plan?**
A **Module** is a topic area (e.g. "Fractions"). A **Practice Plan** combines
one or more modules with a weekly session target and assigns them to students.

**How often should students practice?**
Start with **3 sessions per week**. Adjust based on their progress data in the
Progress Tracker.

**Can a student have multiple Practice Plans?**
No — each student has **one active plan**. Assigning a new one replaces it.

**Can I use decks I already have in Anki?**
Yes. Anything you can export as a shared **`.apkg`** in Anki uploads straight
into AnkiTov.

**What does "smart scheduling" actually do?**
Instead of a fixed "review every 3 days" rule, the system computes, per card,
the moment a student is most likely to be about to forget it, and schedules
the review then. You set *how often* (weekly sessions); it decides *when*.

**Do I control what my students see?**
Yes. You upload the decks, define the modules/plans, and generate the
sessions. Students see exactly what you assign — and only that.

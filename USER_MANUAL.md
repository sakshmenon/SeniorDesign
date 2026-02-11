# Gradly user manual

This manual describes every main part of Gradly and how to use it. For a quick start, see the [User Guide](USER_GUIDE.md).

> **Active development:** Gradly is under active development. Features and screens may change. This manual is updated when we make significant changes; the app itself is the source of truth.

---

## Table of contents

1. [Overview](#overview)
2. [Sign in and sign up](#sign-in-and-sign-up)
3. [Home](#home)
4. [Profile](#profile)
5. [Planning](#planning)
6. [Requirements panel](#requirements-panel)
7. [FAQ](#faq)

---

## Overview

Gradly is a web app that helps you:

- **Plan your semesters** – Organize courses by year and term (Freshman through Senior; Fall, Spring, Summer).
- **Record completed courses** – Mark which classes you’ve already taken and in which semester.
- **Track degree progress** – See how many requirements you’ve completed for your major (when your major is set and requirements are loaded).
- **View credits** – See credits earned and a simple view of progress for the current academic year.

You use it in a browser. After you sign in, you can move between **Home**, **Planning**, and **Profile** using the top navigation bar. Your email appears in the header; you can sign out from there.

---

## Sign in and sign up

### Log in

- Open the app and go to the login page.
- Enter your **email** and **password**.
- Click the button to log in. If the information is correct, you’re taken to the **Home** page.

If you don’t have an account, use the sign-up option instead.

### Sign up

- From the login page, open the **Sign up** page (link or tab).
- Enter your **name**, **email**, and **password**.
- Submit the form. Depending on the app’s configuration, you may need to confirm your email before you can log in.
- After that, log in with the same email and password.

**Terms used:** *Sign up* means creating a new account. *Log in* (or *Sign in*) means opening the app with an existing account.

---

## Home

The Home page is your dashboard after you sign in.

- **Welcome message** – Shows your name or email.
- **Summary cards** (e.g. four tiles):
  - **Degree progress** – Percentage of major requirements completed (based on classes you’ve marked as taken and the requirements list for your major).
  - **Credits earned** – Total credits from all classes you’ve recorded as taken.
  - **Upcoming courses** – Number of classes you’ve added to current or future semesters on the Planning page.
  - **Current year** – The academic year you’re in (e.g. 2025–26).
- **Current year progress bar** – Shows how many credits you’ve completed for the *current academic year* compared to a target (e.g. 30 credits). Only classes you’ve marked as taken in semesters that fall in this year are counted.
- **Requirements summary** – A short line like “Requirements done: X / Y” when your major is set and requirements are loaded.

If you haven’t set a major or added any classes yet, some numbers may be zero or show “Loading…”. Set your major in **Profile** and add or mark classes in **Planning** for the numbers to reflect your progress.

---

## Profile

The Profile page is where you store information Gradly uses for planning and requirements.

**Fields:**

- **Name** – Your display name.
- **Email** – Shown for reference; usually managed by your account and may not be editable here.
- **Age, phone, major, minor, GPA** – Optional. **Major** is the one Gradly uses to show degree requirements (e.g. CS or Computer Science).
- **Freshman semester** – The term and year you started college (e.g. Fall 2024). Required for the Planning page to show your semesters.
- **Planned graduation semester** – The term and year you expect to graduate (e.g. Spring 2028). Required so Gradly knows how many semesters to show.

Use the **term** and **year** dropdowns for the two semester fields, then click **Save profile**. Until Freshman and Graduation semesters are set, the Planning page will prompt you to complete your profile.

---

## Planning

The Planning page is where you see your semesters and add or remove classes.

### Layout

- **Left side (main area):**
  - A **“Search classes…”** bar at the top. Click it to open the search overlay.
  - **Year blocks** – Freshman, Sophomore, Pre-junior, Junior, Senior. Each block has three **semester cards**: Fall, Spring, and Summer. Each card shows the actual term and year (e.g. “Fall 2024”) and a status: **Done** (past), **Active** (current), or **Plan** (future).
- **Right side (narrow panel):** **Requirements** for your major (see [Requirements panel](#requirements-panel)).
- You can **resize** the left and right areas by dragging the vertical divider between them.

If you haven’t set Freshman and Graduation semesters in Profile, you’ll see a message and a link to Profile instead of the plan.

### Search and add a class

1. Click **“Search classes…”**.
2. A window opens in the center of the screen with a search box. Type part of a **course code** or **course title** (e.g. `CS`, `intro`, `calculus`). Results update as you type.
3. In the results list, find the class you want. Click **“Add to semester”**.
4. A **dropdown** appears. Choose the semester (e.g. “Fall 2025”, “Spring 2026”). The class is then added to that semester.
5. **Past semesters:** The class is recorded as **taken** (it appears under “Taken” on that semester card).
6. **Current or future semesters:** The class is recorded as **planned** (it appears in the list for that card and you can remove it with “Remove”).

You can close the search window by clicking **Close** or by clicking the dark area outside the window.

### Remove a planned class

On a semester card, next to a class that is *planned* (not under “Taken”), click **Remove**. The class is removed from that semester only. It is not deleted from the catalog; you can add it again later to any semester.

### Semester statuses

- **Done** – This semester is in the past. You can only record classes as **taken** here (no “planned” list). Add past classes via search → “Add to semester” → choose this semester.
- **Active** – Current semester. You can add planned classes and record taken classes.
- **Plan** – Future semester. You can add and remove planned classes.

---

## Requirements panel

On the right side of the Planning page, the **Requirements** panel shows how you’re doing on your major’s degree requirements.

- **Title:** “Requirements”.
- **Summary line:** “X / Y remaining” – how many requirements are still left out of the total.
- **List of remaining courses** – Course codes (e.g. CS2011, MATH2076) that still count as not completed. Once you add a class with that code as **taken** (in any past or current semester), it can be counted as completed and may disappear from this list (depending on how requirements are set up).
- **Gen Ed:** If your major has general-education slots, a line like “Gen Ed: N slot(s)” may appear.

**When it doesn’t load:** If you see “Loading requirements…” for a long time or “No requirements for [major]”, check that:

1. Your **major** is set in **Profile** (e.g. CS or Computer Science).
2. The app’s backend has requirement data for that major. If you’re running the app yourself, your administrator may need to load requirement data (e.g. for CS) into the database.

The panel is narrow by design; you can drag the divider to give it more or less space.

---

## FAQ

### Do I need to create an account?

Yes. You must sign up and log in so that your plan and progress are saved and tied to your account.

### I forgot my password. How do I reset it?

Password reset is handled by the authentication provider (Supabase). If the app has a “Forgot password?” link on the login page, use that. Otherwise, check the documentation for your deployment or contact whoever manages your Gradly instance.

### Why don’t I see any semesters on the Planning page?

Set **Freshman semester** and **Planned graduation semester** in **Profile** and save. The Planning page needs these so it knows which semesters to show (from your start to your planned graduation).

### Why is the requirements panel empty or stuck on “Loading…”?

- Make sure your **major** is set in **Profile** (e.g. CS or Computer Science).
- Requirements are loaded from the server. If your major isn’t in the system yet, or requirement data hasn’t been loaded for it, the panel may show “No requirements” or keep loading. Contact your administrator if you expect requirements for your major to be available.

### What’s the difference between “taken” and “planned” classes?

- **Taken** – You already completed the class in that semester. Used for past (and optionally current) semesters. These count toward your credits and degree progress.
- **Planned** – You intend to take the class in that semester. Used for current and future semesters. They don’t count as completed until you move them to “taken” (e.g. by adding them to a past semester or a future “taken” flow if the app supports it).

### Can I add a class to a past semester?

Yes. Use **Search classes…** → find the class → **Add to semester** → choose the past semester (e.g. Fall 2023). It will appear under “Taken” on that semester card and can count toward your requirements and credits.

### How is “current year” decided?

The app uses the current date to decide which academic year is “current” (e.g. Fall 2025 – Summer 2026). Credits you’ve recorded as taken in semesters that fall in that year are summed for the “current year” progress bar on Home.

### Will my data be lost if the app changes?

Gradly is under active development. We aim to keep your account and data when we update the app, but we recommend keeping your own record of important plans. Export or backup options may be added in the future.

### I see something in the app that doesn’t match this manual.

The app is the source of truth. This manual is updated when we make significant changes. If something is missing or wrong in the docs, we’ll fix it in a future update.

### Where can I report bugs or ask for features?

That depends on how you use Gradly (e.g. school deployment vs. open source). Check the main project README or ask your administrator for the right place to report issues or request features.

---

*This manual was written for Gradly users. Gradly is under active development; we’ll update this document as the product evolves.*

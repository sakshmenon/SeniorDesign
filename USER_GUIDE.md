# Gradly user guide

This guide helps you get Gradly running and start using it. Gradly is an app for planning your college courses and tracking progress toward your degree.

> **Note:** Gradly is under active development. Screens and options may change as we improve the product. This guide is updated when we make major changes.

---

## What you need

- A modern web browser (Chrome, Firefox, Safari, or Edge).
- If you’re **running Gradly yourself**: Node.js (v18 or newer) and npm. Optionally, a Supabase account and Python if you want to load sample data.

---

## Installation (running Gradly yourself)

Use these steps only if you are setting up Gradly on your own computer or server (for example, for development or a private deployment).

### 1. Get the code and install dependencies

```bash
cd gradly-v3   # or your project folder
npm install
```

This installs the JavaScript packages the app needs.

### 2. Configure Supabase (backend)

Gradly uses [Supabase](https://supabase.com) for sign-in and data storage.

1. Create a free project at [supabase.com](https://supabase.com).
2. In your Supabase project, go to **Settings → API**.
3. Copy the **Project URL** and the **anon public** key.
4. In the Gradly project folder, create a file named `.env` (if it doesn’t exist).
5. Add these lines, using your own URL and key:

   ```
   VITE_SUPABASE_URL=https://your-project.supabase.co
   VITE_SUPABASE_ANON_KEY=your-anon-public-key
   ```

   Keep this file private and do not commit it to version control.

### 3. Run the app

```bash
npm run dev
```

Then open **http://localhost:5173** in your browser. You should see the Gradly login page.

---

## Creating an account

1. On the login page, click **Sign up** (or go to the sign-up page if the link is shown).
2. Enter your **name**, **email**, and **password**.
3. Submit the form.
4. If the app is set up to use email confirmation, check your inbox and confirm your email. Otherwise, you may be able to sign in right away.
5. Sign in with your **email** and **password** on the **Log in** page.

After you sign in, you’ll be taken to the **Home** page.

---

## First steps after sign-in

### Set up your profile

Your profile stores information Gradly uses for planning and requirements.

1. Click **Profile** in the top navigation.
2. Fill in at least:
   - **Freshman semester** – The term and year you started (e.g. Fall 2024).
   - **Planned graduation semester** – When you expect to graduate (e.g. Spring 2028).
3. Optionally add your **major** (e.g. CS or Computer Science). This is used to show degree requirements.
4. Click **Save profile**.

Until these are set, the Planning page will ask you to complete your profile first.

### Look at Home

The **Home** page shows a short overview of your progress:

- **Current year** – A bar showing how many credits you’ve completed for the current academic year versus a target (e.g. 30 credits).
- **Degree progress** – Percentage of requirements completed (if your major is set and requirements are loaded).
- **Credits earned** – Total credits from classes you’ve marked as taken.
- **Upcoming courses** – Number of classes you’ve planned for current or future semesters.

### Add and plan classes (Planning page)

1. Click **Planning** in the top navigation.
2. You’ll see **years** (Freshman, Sophomore, Pre-junior, Junior, Senior). Each year has three terms: **Fall**, **Spring**, and **Summer**.
3. To **search for a class**:
   - Click the **“Search classes…”** bar at the top of the plan.
   - A search window opens. Type part of a course code or title (e.g. `CS` or `intro`).
   - Results appear in the list.
4. To **add a class to a semester**:
   - In the search results, find the class and click **“Add to semester”**.
   - Choose the semester (e.g. Fall 2025) from the dropdown.
   - The class is added to that semester. Past semesters record the class as **taken**; current and future semesters record it as **planned**.
5. To **remove a planned class** from a semester, click **Remove** next to that class on the plan.

The **right panel** on the Planning page shows **Requirements** for your major (e.g. how many required courses are left). Set your major in Profile so this list loads.

---

## Getting help

- For a **detailed description of every page and feature**, see the [User Manual](USER_MANUAL.md).
- For **common questions and answers**, see the [FAQ in the User Manual](USER_MANUAL.md#faq).

Gradly is still evolving; we’ll update this guide as we add features and change the interface.

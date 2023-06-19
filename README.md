# Sveltekit Firebase Template

A simple skeleton for a Sveltekit Firebase stack. The original project was created by following this [tutorial](https://www.youtube.com/watch?v=TIbL0VOE900) and then bringing it back to bare-bones.

## Set-up

Clone the repo locally:

```bash
git clone https://github.com/merryface/sveltekit-firebase-template
```

Install dependencies:

```bash
npm install
```

The firebase project and DB need to be set-up and then hooked up to within the project.

1. Go to the [Firebase Website](https://firebase.google.com/)
2. Click on "Go to Console." Login or create an account as needed
3. Click on "+ Add Project"
4. Name the project and hit next
5. Google analytics as required
6. Once redirected, click on "Authentication", then "Get Started" on the new page
7. Click on "Sign-in method" toggle "Email/Password" ON
8. Go back to "Project Overview" then "Database" -> "Create database"
9. Pick test or production mode
10. Select a location for the DB then wait for the provisioning
11. Go back to "Project Overview" and click on the web link `</>`
12. Register your app name, and keep the tab open
13. Go into your project locally and rename `.env_example` to `.env`
14. Inside `.env`, replace the placeholder values with the values shown in the firebase webpage

Run the project to test (`npm run dev`). You should be redirected to the homepage, which is the login page. Any attemps to go into `/dashboard` should redirect the browser back to the login page until you create an account and login. You can check the stored data in Firebase by going to the project's "Firebase Database" and inspecting the DB in the Panel view.

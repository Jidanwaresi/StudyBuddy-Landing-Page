# StudyBuddy Landing Page

A responsive landing page for StudyBuddy, a study planner app concept. Built with HTML, Tailwind CSS and a little vanilla JavaScript. This is a front end only project, so there is no backend.

**Live demo:** https://jidanwaresi.github.io/StudyBuddy-Landing-Page/

## Features

- Responsive layout for mobile, tablet and desktop using Tailwind breakpoints
- Hero section whose background image adapts to different screen sizes and aspect ratios
- Feature cards, Popular Tools cards and a testimonial section
- Navbar links with an animated underline on hover
- Newsletter form with instant visual feedback after submit
- Touch friendly behavior on phones (no accidental text selection, tap feedback on buttons)

## Tech Stack

| Area | Tools |
| --- | --- |
| Markup | HTML5 |
| Styling | Tailwind CSS (built with the CLI into `src/output.css`) |
| Interaction | Vanilla JavaScript |
| Icons | Remix Icon, Font Awesome, Hugeicons |
| Font | Inter (Google Fonts) |
| Hosting | GitHub Pages |

## Project Structure

```
StudyBuddy-Landing-Page/
├── assets/          # hero-img.png, footer.avif
├── src/             # Tailwind input file and generated output.css
├── index.html       # all page sections and the subscribe script
├── package.json
└── README.md
```

## Run Locally

```bash
git clone https://github.com/jidanwaresi/StudyBuddy-Landing-Page.git
cd StudyBuddy-Landing-Page
npm install
npx @tailwindcss/cli -i ./src/input.css -o ./src/output.css --watch
```

Then open `index.html` in your browser (or use the Live Server extension in VS Code).

## Problems I Solved

| Problem | Solution |
| --- | --- |
| Background image and content slipping out of alignment on different screens | Used a gradient overlay with `bg-cover` on small screens, and a fixed aspect ratio with `bg-contain` on large screens |
| No backend, but the newsletter form still needed feedback | A submit handler calls `event.preventDefault()`, shows a confirmation alert and resets the form. It does not store or send any email. |
| `:active` button feedback worked in DevTools but not on a real phone | Added an empty `ontouchstart` attribute to the `body` tag, a known workaround that makes `:active` styles register on touch |
| Text and UI elements getting selected while scrolling on mobile | Applied Tailwind's `select-none` utility to the affected sections |

## What I Learned

- A layout that looks right on one screen can break on another, so backgrounds need testing across aspect ratios.
- DevTools is useful, but touch behavior needs a real device.
- JavaScript can give instant front end feedback, but storing emails needs a backend.
- How to collaborate on GitHub with a teammate: pull requests, code review and merging into the main branch.

## Known Limitations

- The testimonial arrows and dots, the mobile menu icon, and most links (`href="#"`) are placeholders and not wired up yet
- The newsletter form shows a confirmation only and does not save emails
- The testimonial photo is loaded from an external URL

## Contributors

- **Jidan Waresi** ([@jidanwaresi](https://github.com/jidanwaresi)): navbar, hero, features, popular tools, testimonials, newsletter interaction, mobile fixes
- **Mukesh Choudhary** ([@mukeshcoderhub](https://github.com/mukeshcoderhub)) : built the initial footer section and sent it as a pull request, which I reviewed and merged

## Acknowledgements

Built as part of the Beyond Sigma program by Not Your College (Sheryians Coding School). Thanks to my frontend mentor Devendra Dhote.

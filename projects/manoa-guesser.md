---
layout: project
type: project
image: img/manoa-guesser/landing_page.png
title: "Manoa Guesser Web Application"
date: 2025
published: true
labels:
  - Bootstrap
  - React
  - Next.js
  - Software Engineering
summary: "Final project for ICS 314."
---

<div class="text-center p-4">
  <img width="400px" src="../img/manoa-guesser/homepage.png" class="img-thumbnail" >
  <img width="400px" src="../img/manoa-guesser/admin.png" class="img-thumbnail" >
  <img width="400px" src="../img/manoa-guesser/admin2.png" class="img-thumbnail" >
</div>

Manoa Guesser is a gamified exploration web application designed to help students at the University of Hawaiʻi at Mānoa become more familiar with campus locations. Players are shown photos taken around campus and must guess where each photo was taken using an interactive map. The goal of the project is to make learning the campus layout more engaging through friendly competition, while also allowing the community to contribute new content through photo submissions that are reviewed by administrators.

## Designing the Player Experience and Navigation

My contributions to Manoa Guesser focused primarily on improving the user experience, strengthening navigation, and building out admin and moderation functionality to support  use of the application.

I designed and implemented the home and landing page to introduce the app in a clear and welcoming way. This page includes a strong visual theme, a concise description of the game’s purpose, and clear paths for users to start playing, sign in, or explore other features. The goal was to make the app immediately understandable for first-time users rather than dropping them into gameplay without context.

In addition to the landing page, I updated the navigation bar to support smoother movement between core pages such as Home, Game, Leaderboard, and Submission. I focused on keeping the layout clean, consistent, and responsive so that users could always understand where they were in the app and easily move between features. Alongside this, I refined the login and signup pages to provide a more polished and consistent experience while keeping all authentication logic fully intact.

<img width="600px" src="../img/manoa-guesser/homepage.png" class="img-thumbnail" >

## Building Admin Tools and Moderation Workflows

A large portion of my work involved building the foundation for admin functionality. I implemented a responsive admin dashboard using React-Bootstrap layout components, creating a clean structure that can scale as more administrative features are added. I also created admin-only edit pages that allow administrators to update user and game-related data. These pages load existing records, present them in clear forms, enforce basic validation, and provide confirmation or error feedback after updates are submitted.

I also worked on content moderation features to support the community-driven nature of the app. I connected the admin interface to image submission data so administrators can view pending images with relevant details, approve or delete submissions, and see the interface update correctly when there are no items to review. To complement this, I added a user image reporting system that allows players to flag inappropriate or incorrect images. These reports are surfaced in the admin interface with key information so administrators can make quick moderation decisions.

<img width="600px" src="../img/manoa-guesser/admin2.png" class="img-thumbnail" >
<img width="600px" src="../img/manoa-guesser/admin.png" class="img-thumbnail" >

## Refining Accounts, Data, and Long-Term Maintainability

Finally, I made several account and maintenance-related improvements. I implemented username selection during user sign-up and enforced uniqueness to prevent duplicate usernames. I also updated the Edit User page styling to better match the rest of the application without changing its functionality. Additionally, I removed outdated score-editing functionality after scoring was migrated to a new Prisma database, helping reduce confusion and eliminate broken UI elements.

## Takeaways From a Real Team Project

Working on Manoa Guesser helped me better understand how real software projects evolve beyond simply adding features. I learned how important consistency is when multiple people are contributing to the same application, especially in terms of layout, navigation, and visual design. Establishing shared patterns early makes the app easier to maintain and extend over time.

I also gained experience designing admin and moderation tools, which require more careful consideration than standard user-facing features. These tools must be secure, reliable, and clear, since mistakes can directly affect users and content quality. Overall, this project reinforced that good software engineering is about building systems that are not only functional, but also maintainable, scalable, and easy for both users and developers to work with.

Learn more from our [Manoa Guesser GitHub](https://manoa-guesser.github.io/).
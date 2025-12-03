---
layout: essay
type: essay
title: "The Code Patterns I Didn’t See Coming"
# All dates must be YYYY-MM-DD format!
date: 2025-12-03
published: true
labels:
  - Learning
  - Design
---

<img width="400px" class="rounded float-start pe-4" src="../img/design/design.png">

## Manoa Guesser App
When we were building Manoa Guesser, I started noticing that our codebase was slowly turning into a messy garage. There were files all over the place, random logic shoved into components it didn’t belong in, and every time something broke we had to dig through layers of confusion just to find out why. It wasn’t that our code was “bad,” it was more that the structure wasn’t really planned out. We were given good templates at the start, but once we tried adding real features, things fell apart pretty quickly.

That’s when I started actually paying attention to design patterns. Before this, design patterns honestly felt like one of those textbook terms that only matter on exams or in job interviews. But the more our project grew, the more I realized design patterns are really just the solutions to problems that people figured out a long time ago. They’re not copy-paste code or super formal rules. They’re more like useful habits you pick up after messing up enough times. Kind of like how every lab report ends up looking the same, the structure just works, so everyone ends up naturally following it.

## Unintentional Design Patterns
At first, I didn’t even notice I was using design patterns. They just sort of sneak in when your project gets big enough.

For example, Next.js pretty much pushes you into the Front Controller pattern without even mentioning the name. Every request gets funneled through the same pipeline before it reaches your code. At first it felt restrictive, but then I realized it actually saved us. Having all the authentication and admin checks in one place prevented us from rewriting the same logic in every single API route. It’s like having one main entrance to a building instead of twelve different doors where things can slip through unnoticed.

MVC also showed up naturally. Prisma handled the data (the Models), our API routes acted like Controllers, and the React components were the Views. It just makes sense when you’re building anything that has a UI, a database, and logic in between. Once you see it happening, it’s pretty hard to unsee.

When parts of the system had to react to changes, that’s where I started noticing Observer and Publish-Subscribe patterns. Things like state updates, score changes, admin approvals, or even UI rerenders after a fetch they all follow the same idea. One thing updates, and the rest of the system reacts. Instead of constantly checking, “Did something change yet?”, you just wait for the update and everything else takes care of itself.

For the gameplay logic, we basically built a Factory without realizing it. The game needs location data, but the game shouldn’t have to understand Prisma models or how data is stored in the database. So we made a function that just creates a clean, game-ready object. It’s a small thing, but it made the rest of the game logic much simpler.

React also makes heavy use of the Prototype idea. You make one clean component—like a card, a button, a table row—and then reuse it everywhere with slightly different props. It’s like copying a template instead of rewriting everything from scratch. Once you get used to it, it saves a lot of time and keeps everything looking consistent.

Some patterns weren’t obvious at all until someone pointed them out. For example, Prisma’s client is basically a Singleton. You create it once, reuse it, and avoid creating a ton of unnecessary database connections that slow everything down. It’s one of those things that just quietly does its job in the background.

## Final Thoughts
By the end of Milestone 2, design patterns finally started clicking for me. They’re not these strict rules that you memorize—they’re just common ways people solve the same problems over and over again. And honestly, once you start using them, you see why they’ve stuck around for so long. They keep your code from collapsing on itself.

In Manoa Guesser, we ended up using a mix of Front Controller, MVC, Singleton, Observer, Publish-Subscribe, Factory, and Prototype, even without saying those names out loud. They kind of became the hidden structure that held everything together. And after experiencing what happens without structure, I’d definitely rather build things using patterns than keep reinventing chaos every time.
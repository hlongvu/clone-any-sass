# clone-any-sass

what are the exact steps to clone any SaaS?

most people overcomplicate this. 

here's the exact playbook I'd use with Claude Opus 4.5 + Factory AI to reverse engineer and rebuild any SaaS in weeks, not months:

## step 1: deep product archaeology

before writing a single line of code, you need to understand what you're cloning at a forensic level.

- sign up for the target SaaS (free trial, paid, whatever)
- screen record yourself using every single feature
- document every UI state, error message, edge case
- export any data they let you export (reveals data models)
- check their docs, API references, changelog

feed all of this into Claude Opus 4.5. upload screenshots, paste documentation, describe workflows. ask it to reverse engineer the likely database schema, identify core entities, map user flows.

## step 2: technical reconnaissance

- check their job postings (reveals tech stack)
- Wappalyzer / BuiltWith for frontend frameworks
- check network tab for API structure and naming conventions
- look at their public GitHub if they have one
- read their engineering blog posts

paste all findings into Claude. ask: "based on this evidence, what's the likely architecture? what are they probably using for auth, payments, background jobs, file storage?"

## step 3: scope ruthlessly

this is where most people fail. they try to clone 100% of features.

use Claude to categorize every feature you documented into:

core (MVP): the 3-5 features that deliver 80% of the value

important: nice to have, build in month 2-3

bloat: features you'll never build (or build last)

be honest. most SaaS products have years of feature creep. you're building the lean version that solves the same core problem.

## step 4: architecture design with Claude

now you prompt Claude Opus 4.5 with everything you've gathered:

"I'm building a clone of [X]. here's what I know about their product: [paste everything]. here's my MVP scope: [paste features]. design me a complete technical architecture including:

- database schema with all tables and relationships
- API endpoint structure
- auth flow
- file storage approach
- background job requirements
- third party integrations needed
- suggested tech stack optimized for solo dev speed"

Claude will give you a comprehensive architecture doc. iterate on it. ask follow-up questions. poke holes in it.

## step 5: Factory AI for accelerated build

this is where Factory AI comes in. Factory is built for autonomous software development at scale.

set up your repo. connect Factory. feed it the architecture Claude designed.

use Factory to:

- scaffold the entire project structure
- generate database migrations from your schema
- build out API endpoints with proper validation
- create UI components from your screenshots
write tests as you go

Factory's agents work continuously. you review PRs, provide feedback, they iterate.

## step 6: the "screenshot to code" workflow

for UI, the fastest path:

screenshot every page of the target SaaS

feed to Claude: "recreate this UI in React/Next.js + Tailwind. make it pixel-close but don't infringe on their specific brand assets. use placeholder copy."
Claude outputs component code

Factory agents refine and integrate into your codebase
repeat for every screen

you can rebuild entire dashboards in hours, not days.

## step 7: data model validation

before going deep on build, validate your data model:

- create seed data scripts
- simulate real user workflows in your local env
- ask Claude: "here's my schema, here are the user workflows. what edge cases am I missing? what will break at scale?"

fix issues now, not after you have users.

## step 8: auth, payments, core infra

don't reinvent these. use boring, reliable tools:

- auth: Clerk, Supabase Auth, or NextAuth
- payments: Stripe (just use Stripe)
- email: Resend or Postmark
- file storage: S3 / Cloudflare R2
- database: Postgres (Supabase, Neon, or Railway)
- hosting: Vercel for frontend, Railway/Render for backend

prompt Claude: "generate the complete integration code for [Stripe/Clerk/etc] in my [framework]. include webhook handlers, error handling, and TypeScript types."

## step 9: rapid iteration cycles

your daily workflow:

morning:

- review Factory AI's overnight PRs
- merge what's good, comment on what needs changes
- add new tasks to the queue

afternoon:

- work on complex features manually with Claude as copilot
- screen share with Claude (via screenshots) when stuck
- let Factory handle the more routine build-out

evening:

- test the day's work
- document bugs and edge cases
- queue up tomorrow's Factory tasks

## step 10: the 80% product in 2-3 weeks

if you're disciplined, you'll have a functional clone of the core product in 2-3 weeks. it won't have every feature. it doesn't need to.

what you'll have:

- working auth and user management
- core product functionality (the main 3-5 features)
- payments and billing
- basic admin/dashboard
- deployable to production

## step 11: differentiate or die

here's the truth: a pure clone is a commodity race to the bottom.

once you have the base, you need your angle:

- price: can you be 50% cheaper?
- niche: can you serve one segment 10x better?
- speed: can your UX be dramatically faster?
- integration: can you plug into a workflow they ignore?
- model: can you flip the business model (one-time vs subscription, usage-based, etc)?

use Claude to brainstorm differentiation: "I cloned [X]. here's what they do. what are their biggest customer complaints (search Reddit, Twitter, G2 reviews)? where could a competitor win?"

## step 12: launch and iterate

ship to a small group. friends, Twitter followers, a Discord community. get feedback fast.

use Claude to:

- analyze feedback patterns
- prioritize feature requests
- draft changelog and marketing copy
- debug issues in production

the meta-lesson

the tools have changed everything. what used to take a funded team 6-12 months, a single operator with Claude Opus 4.5 + Factory AI can do in weeks.

but the leverage only works if you:

- scope ruthlessly (most important skill)
- move fast and iterate
- use AI for acceleration, not as a crutch
- actually understand what you're building

the people who win are the ones who treat AI as a 10x multiplier on their existing skills, not a replacement for thinking.

now go clone something and undercut an incumbent.

Source: [caiden](https://x.com/pipelineabuser/status/2007823424740352425)

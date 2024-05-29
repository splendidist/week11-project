✨ https://week11-project.vercel.app/ ✨

## Upvote

Upvote is a Reddit-esque web application that allows users to create posts, upvote and downvote posts, and comment on posts in a multi-threaded, nested list.

The project is built using Next.js with the /app router and [Tailwind CSS](https://tailwindcss.com/), and uses [Auth.js (formerly Next Auth)](https://authjs.dev/) for user authentication. The data is stored in a Postgres database, which is created and accessed with raw SQL queries using the `pg` package.

The project is a work in progress and is not yet complete.

## Features

- [x] View a list of posts
- [x] View a single post
- [x] Create a post
- [x] Upvote and downvote posts
- [x] Pagination of posts
- [x] Comment on posts
- [x] Nested comments (recursive lists)
- [x] User authentication

## Setup instructions

1. Fork the repository (check "copy the main branch only") and clone your fork to your local machine
2. In your forked repository, copy the SSH key and clone the repo into your terminal (git clone SSHKey)
3. cd projectname, code .
4. Run `npm i` in the terminal
5. Create a `.env.local` file in the root directory, and copy and paste the template from the ".env.example" file
6. Set the AUTH_SECRET: to be anything, using only letters and numbers
7. In Github, go to your account, then settings, the developer settings, then new github app.
8. Name the app
9. Temporarily set the Homapage URL to http://localhost:3000 and the callback URL to http://localhost:3000/api/auth/callback/github
10. Enable request user authorization and disable webhook
11. Click create github app
12. Copy the client id and paste it in your ".env.local" file in AUTH_GITHUB_ID:
13. Generate a client secret and paste it in your ".env.local" file in AUTH_GITHUB_SECRET:
14. Go to supabase.com, and in your account go to connect, then connection string, url, and copy and paste this URL and paste it in your ".env.local" file in DATABASE_URL:
15. Swap [password] for your supabase database password (to reset this, go to settings, then database, then reset database password)
16. In supabase, open the query editor and paste the contents of schema.sql (remove the -- from line 79)
17. Run `npm run dev` to start the development server
18. Open [http://localhost:3000](http://localhost:3000) with your browser to see the site
19. On Vercel.com, click new project, then link your github repo, and paste the environmental keys before pressing deploy
20. In github, change the Homepage URL to your new vercel link, and the callback URL to your new vercel link + /api/auth/callback/github

## Potential future features

- [ ] User profiles
- [ ] Sorting posts by recent (date posted), top (most upvotes), and most controversial (most upvotes _and_ downvotes)
- [ ] User karma scores
- [ ] User badges / trophies (awards for achievements like number of posts, years on the site, etc.)
- [ ] User settings (eg. number of posts per page, theme, etc.)
- [ ] Moderation tools / reporting or flagging objectionable comments for removable by admins
- [ ] Searching posts (possibly using simple SQL LIKE '%some search%', or [Postgres text search](https://www.crunchydata.com/blog/postgres-full-text-search-a-search-engine-in-a-database))
- [ ] Subreddits (separate communities, that isn't just one big list of posts, that can be created by users)
- [ ] User notifications
- [ ] User private messaging
- [ ] User blocking
- [ ] User following
- [ ] User feed (posts from users you follow)
- [ ] User flair

🎯 Please mention the requirements you met and which goals you achieved for this assignment.

Requirements

- Deploy to Vercel

Stretch Goals

- Fix page titles on post pages to match the post title - I used generateMetaData to make the post title appear on the tab as the page title e.g Didit | Post Title

🎯 Were there any requirements or goals that you were not quite able to achieve?

I wanted to try to fix the upvote error but ran out of time

🎯 If so, could you please tell us what was it that you found difficult about these tasks?

I found the stretch goal of making the page title match the post title difficult, but I may have been testing it on my vercel deploy rather than my local

✨ What went really well and what could have gone better?

Following the steps in order really helped make things go well, and I think my stretch goal could have gone better as I just copy and pasted my query from the edf, but I'm not sure if it can be a more simple query

✨ Detailing useful external sources that helped you complete the assignment (e.g Youtube tutorials).

Metadata - https://techeducators.moodlecloud.com/mod/lesson/view.php?id=1193

✨ Describing errors or bugs you encountered while completing your assignment.

Unhandled Runtime Error
Error: getaddrinfo ENOTFOUND mypostgresconnectionstring
I had this error after running npm run dev because I hadn't saved the .env.local file

✨ Requesting feedback about a specific part of your submission.

Could I get some feedback on the generateMetaData in post->page.jsx

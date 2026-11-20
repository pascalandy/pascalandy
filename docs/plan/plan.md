# Profile upgrade plan

Goal: a visitor to https://github.com/pascalandy understands in 10 seconds who Pascal is and what he builds

Done when:

- The bio and the profile README say what Pascal builds today
- The profile shows 4 pins, and each pinned README is clear to a stranger on its first screen, with its illustration
- The banner and the 4 close-ups look like one family
- mixtape is public, with no secret and no private machine detail

Out of scope: repos that are not pinned, and any automation of the profile

## Decisions

- Pins, in this order: nicely, mixtape, skills, pascalandy-blog-paper. Why: they are the current work. uao is unpinned
- Bio: "Building CLI tools and agent skills that humans and AI agents run equally well · Montréal"
- All public text is in English. Why: the audience is international. The skills repo already links a French guide
- Profile README: short and plain, after charliermarsh and steipete. A banner, 2 intro sentences, a "Start Here" list of the 4 pins with one line each, one "Also" line (pi-journey, uao, html-publish), and links to the blog and the French guide of skills. No badges and no stats widgets. Why: minimal profiles read as professional for tool builders
- Images: AI-generated, 2:1, so that one file is both the README hero and the 1280x640 social preview. One version only, because cream paper reads well on the dark theme
- Image style, the same words for each image: "precise isometric technical illustration, fine ink linework on warm cream paper, flat muted colors (sage, slate, oak), a single warm amber accent on lit windows and the human moment, true 30-degree isometric projection, no perspective." No text, letters, numbers, logos or UI. One adult man, small or from behind, never a recognizable portrait
- Banner: a tall, narrow tower-house. Each floor is one pin: a nicely workshop with tools and a server rack, a mixtape listening room with records and cassettes, a skills library, and a blog writing desk. On the roof, the man from behind, in the amber light. Each close-up is a zoom on one floor. Why: one picture shows all the work, and the close-ups keep the family

## Steps

Pascal does the steps marked "Pascal". An agent does the other steps. Each agent step that changes a repo is one PR in that repo.

1. Pascal: run `gh auth refresh -h github.com -s user` and approve in the browser. Why: an agent needs this scope to change the bio
2. Agent: set the bio with `gh api -X PATCH user -f bio="..."`
3. Pascal: pin nicely, skills and pascalandy-blog-paper, in this order, and unpin uao. Why: GitHub has no API for profile pins
4. Agent: give the 4 pinned repos an English description and topics, and set the blog repo homepage to https://blog.pascalandy.com
5. Agent: make mixtape ready to go public, in one PR:
   - Rewrite the README for a stranger: what it does, how to install it, a first sync
   - Remove machine names, local paths and internal milestones from every tracked file
   - Add the MIT license
6. Agent: before the visibility change, scan the full mixtape history, issues and PRs for secrets and private details. Report only pass or fail on GitHub
7. Pascal: if step 6 passes, make mixtape public and pin it second
8. Agent: make 3 static HTML mockups of the profile README. Pascal picks one
9. Agent: write `README.md` in this repo from the picked mockup, with the banner slot empty. Caution: GitHub shows a non-empty `README.md` on the profile at once
10. Agent: rewrite the top of each pinned README: hero slot, one-line pitch, install, a minimal example
11. Agent: make banner drafts. Pascal picks one. The agent adds it to `README.md`
12. Agent: make close-up drafts from the picked banner. Pascal picks one for each floor. The agent adds each one to its repo as `docs/assets/hero.png`
13. Pascal: upload the same 5 files as social previews in each repo's Settings: each close-up on its pin, and the banner on this repo. Why: GitHub has no API for this upload

## Later

Update this plan when a pin changes: a new floor for the banner, a new close-up, and a new "Start Here" line

# Profile upgrade plan

Help a visitor to https://github.com/pascalandy see who Pascal is and what he builds in 10 seconds.

## Decisions

- Pin `nicely`, `mixtape`, `skills`, and `pascalandy-blog-paper` in that order
- Write public text in English
- Keep the profile README to a banner, 2 intro sentences about what Pascal builds, and a **Start Here** list of only the 4 pins in pin order. Give each repo one line with its link and what it does. Put the blog link and the French guide already linked from `skills` on their matching lines
- Generate 5 images with AI. Export each as a 1280 × 640 PNG under 1 MB for use in both a README and its repo's social preview
- Reuse the prompt "precise isometric technical illustration, fine ink linework on warm cream paper, flat muted colors (sage, slate, oak), a single warm amber accent on lit windows and the human moment, true 30-degree isometric projection, no perspective" for all 5 images. Keep text, letters, numbers, logos, and UI out of the art
- Show a tall, narrow tower-house with 4 floors. In pin order from bottom to top, show a workshop with tools and a server rack, a listening room with records and cassettes, a library, and a writing desk. Show one adult man from behind on the roof in amber light. Frame each close-up as a zoom into its matching floor

## Steps

Use one PR per repo for the file changes. All 5 repos belong to `pascalandy`.

1. **Pascal**. Sign in to `gh` as `pascalandy`, run `gh auth refresh -h github.com -s user`, and approve the request in the browser
2. **Agent**. Run `gh api --hostname github.com user --jq .login`. If it returns `pascalandy`, run `gh api --hostname github.com -X PATCH user -f 'bio=Building CLI tools and agent skills that humans and AI agents run equally well · Montréal' --jq .bio`. Check that the returned bio matches
3. **Agent**. Draft 3 local HTML mockups of the profile README using `charliermarsh` and `steipete` as layout references. Pascal picks one
4. **Agent**. Draft the banner for the chosen layout. After Pascal picks a banner, use it as the reference for the 4 close-ups. Pascal picks one per floor. Export the 5 chosen images to the specs above
5. **Agent**. In each pin, save the close-up as `docs/assets/hero.png` and show it at the top of `README.md`. Follow it with a one-line pitch, setup instructions, and one working example. Check that the image renders and the example works. For `mixtape`, show a first sync, add the MIT license, and remove secrets, private details, and internal milestones from all tracked files in the same PR
6. **Agent**. After the `mixtape` PR merges, check all Git history, including every branch, tag, and PR commit. Check issues, PRs, comments, releases, and [other content GitHub will make public](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility#changing-from-private-to-public). If you find a secret, a private detail, or anything you cannot review, the check fails. Report only `pass` or `fail` on GitHub
7. **Pascal**. If anything has changed since the review, repeat step 6. With a passing review, make `mixtape` public under **Settings** → **Danger Zone** → **Change visibility**. Check that `mixtape` opens when signed out. On your profile, choose only the 4 repos under **Customize your pins**, save, and drag them into the order above
8. **Agent**. Add the chosen layout as the root `README.md` in `pascalandy/pascalandy`, with the banner at `docs/assets/banner.png` in the same PR. After merge, open the profile signed out and check the bio, 4 pins, banner, and all README links
9. **Pascal**. In each repo, use **Settings** → **Social preview** → **Edit** → **Upload an image**. Use the banner for `pascalandy/pascalandy` and each close-up for its pin. Check each preview shows the right image

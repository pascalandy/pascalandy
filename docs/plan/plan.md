# Profile upgrade plan

Help a visitor to https://github.com/pascalandy see who Pascal is and what he builds in 10 seconds.

## Decisions

- Pin `nicely`, `skills`, and `pascalandy-blog-paper` in that order
- Write public text in English
- Keep the profile README to a banner, 2 intro sentences about what Pascal builds, and a **Start Here** list of only the 3 pins in pin order. Give each repo one line with its link and what it does. Put the blog link and the French guide already linked from `skills` on their matching lines
- Generate 4 images with AI: 1 banner and 3 close-ups. Export each as a 1280 × 640 PNG under 1 MB for use in both a README and its repo's social preview
- Reuse the prompt "precise isometric technical illustration, fine ink linework on warm cream paper, flat muted colors (sage, slate, oak), a single warm amber accent on lit windows and the human moment, true 30-degree isometric projection, no perspective" for all 4 images. Keep text, letters, numbers, logos, and UI out of the art
- Show a tall, narrow tower-house with 3 floors. In pin order from bottom to top, show a workshop with tools and a server rack, a library, and a writing desk. Show one adult man from behind on the roof in amber light. Frame each close-up as a zoom into its matching floor

## Steps

Use one PR per repo for the file changes. All 4 repos belong to `pascalandy`.

1. **Pascal**. Done on 2026-11-20: `gh` has the `user` scope
2. **Agent**. Done on 2026-11-20: the bio reads "Building CLI tools and agent skills that humans and AI agents run equally well · Montréal"
3. **Agent**. Draft 3 local HTML mockups of the profile README using `charliermarsh` and `steipete` as layout references. Pascal picks one
4. **Agent**. Draft the banner for the chosen layout. After Pascal picks a banner, use it as the reference for the 3 close-ups. Pascal picks one per floor. Export the 4 chosen images to the specs above
5. **Agent**. Set a one-line English description on each of the 3 pins with `gh repo edit pascalandy/<repo> --description "..."`, because a pin card shows it. Then, in each pin, save the close-up as `docs/assets/hero.png` and show it at the top of `README.md`. Follow it with a one-line pitch, one way to get started (for `skills`, its existing prompt), and one example. Check that the image renders and the example works
6. **Pascal**. On your profile, choose only the 3 repos under **Customize your pins**, save, and drag them into the order above
7. **Agent**. Make sure the 3 README PRs of step 5 are merged, and open each pinned repo signed out to check its header. Then add the chosen layout as the root `README.md` in `pascalandy/pascalandy`, with the banner at `docs/assets/banner.png` in the same PR. After merge, open the profile signed out and check the bio, 3 pins, banner, and all README links
8. **Pascal**. In each repo, use **Settings** → **Social preview** → **Edit** → **Upload an image**. Use the banner for `pascalandy/pascalandy` and each close-up for its pin. Check each preview shows the right image

## Later

To add a pin, add a floor to the banner, make its close-up, and add its line to **Start Here**

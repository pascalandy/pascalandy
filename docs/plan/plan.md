# Profile upgrade plan

Help a visitor to https://github.com/pascalandy see who Pascal is and what he builds in 10 seconds.

## Decisions

- Pin `pascalandy-blog-paper`, `skills`, `nicely`, and `uao` in that order
- Write public text in English
- Keep the profile README to a banner, 2 intro sentences about what Pascal builds, and a **Start Here** list of `nicely`, `skills`, and `pascalandy-blog-paper`, in that order. Give each repo one line with its link and what it does. Put the blog link and the French guide already linked from `skills` on their matching lines
- Generate 5 images with AI: 1 banner and 4 close-ups, with 2 variants per close-up for Pascal to pick before merge. Export each as a 1280 × 640 PNG under 1 MB for use in both a README and its repo's social preview
- Reuse the prompt "precise isometric technical illustration, fine ink linework on warm cream paper, flat muted colors (sage, slate, oak), a single warm amber accent on lit windows and the human moment, true 30-degree isometric projection, no perspective" for every render. Keep text, letters, numbers, and logos out of the art; screens show abstract lines only
- Show a tall, narrow tower-house with high ceilings, anchored in nature that fills the whole frame, such as forest, rock and water, in the same palette and linework. Set it on a stone foundation with a path to the door, plants over its base and trees at the scale of its floors. Show a home gym on the ground floor and a double-height library above it. On the roof terrace, with plants and a railing, put Pascal's real workstation under a pergola: a large monitor of terminals, a laptop, a mechanical keyboard and three mini-PCs. Show one adult man from behind or in three-quarter view, seated at that desk in amber light. Frame each close-up as a zoom into one part of the tower or its setting

## Steps

Use one PR per repo for the file changes: one for the profile and one for each of the 4 pins. All 5 repos belong to `pascalandy`.

1. **Pascal**. Done on 2026-11-20: `gh` has the `user` scope
2. **Agent**. Done on 2026-11-24: the bio reads "Security consultant | AI-native builder | Montréal"
3. **Agent**. Draft 3 local HTML mockups of the profile README using `charliermarsh` and `steipete` as layout references. Pascal picks one
4. **Agent**. Draft the banner for the chosen layout. After Pascal picks a banner, use it as the reference for the 4 close-ups. Pascal picks one per pin. Export the 5 chosen images to the specs above
5. **Agent**. Set a one-line English description on each of the 4 pins with `gh repo edit pascalandy/<repo> --description "..."`, because a pin card shows it. Then, in each pin, save the close-up variants as `docs/assets/hero-v2a.png` and `hero-v2b.png`, keep any previous `hero.png`, and show the chosen one at the top of `README.md`. Follow it with a one-line pitch, one way to get started (for `skills`, its existing prompt), and one example. Check that the image renders and the example works
6. **Pascal**. On your profile, choose only the 4 repos under **Customize your pins**, save, and drag them into the order above
7. **Agent**. Make sure the 4 README PRs of step 5 are merged, and open each pinned repo signed out to check its header. Then add the chosen layout as the root `README.md` in `pascalandy/pascalandy`, with the banner at `docs/assets/banner-v5c.png` in the same PR. After merge, open the profile signed out and check the bio, 4 pins, banner, and all README links
8. **Pascal**. In each repo, use **Settings** → **Social preview** → **Edit** → **Upload an image**. Use the banner for `pascalandy/pascalandy` and each close-up for its pin. Check each preview shows the right image

## Later

To add a pin, make its close-up from the tower and add its line to **Start Here**

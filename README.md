# OUA Fantasy — League HQ (preview)

Designed and created by Emily Wright.

© 2026 Emily Wright. Original website design and custom application code. All rights reserved.

This is an unofficial, non-commercial fantasy volleyball project for fun with friends. It is not affiliated with, sponsored by, or endorsed by Ontario University Athletics (OUA), any university, or their athletics programs. University names, logos, player information and competition statistics may belong to their respective rights holders. This notice does not claim rights in third-party content.

## Publish preview on GitHub Pages

Create a **new** public repo called `oua-fantasy-league`, upload `index.html`, go to Settings → Pages → Deploy from a branch → `main` → `/(root)`. The published preview is at `https://YOUR-USERNAME.github.io/oua-fantasy-league/`.

## IMPORTANT — preview only

This website is **not connected** to Supabase. It has no real logins, real roster updates, bidding, standings, live scoring, or shared transactions. Example athletes are not actual draft allocations. Do **not** rely on this preview for league operations or enter sensitive information. The existing Draft Scout and tomorrow's Draft Room remain unaffected.

## Proposed production authentication

1. In the *existing* Supabase project, create six Auth users or send invitation emails to each GM; each user sets their own password.
2. Maintain a server-side manager mapping from `auth.users.id` to the corresponding manager ID, secured by RLS.
3. Each logged-in GM can edit only their own lineup and submit only their own waiver bids. Managers may view public rosters and standings. Only the commissioner may resolve waivers or modify league settings.
4. Enforce lineup slot counts, transaction consistency, private sealed bids, roster deadlines, and spending in database functions. Never trust the client UI alone.
5. Import final verified draft ownership from the existing Supabase draft tables after draft night, with player/OUA team IDs.

Keep secrets and passwords out of the public repo. Continue with the exact same Supabase project and create *separate* league tables, rather than altering tomorrow's draft tables.

OUA Fantasy League HQ — Website preview

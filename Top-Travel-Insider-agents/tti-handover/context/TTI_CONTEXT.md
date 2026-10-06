# Top Travel Insider: project context

Background for any Claude working in this folder. Prepared from the planning work done in Claude chat, October 2026.

## Goal
Repopulate toptravelinsider.com with new "Top 10" listicles (destinations, day trips, places to eat and drink). Existing older posts are not being edited; the focus is new posts only.

## Roles
- **tti-writer (subagent):** SEO research through SE Ranking, plus writing and fact-checking. Saves finished Markdown to the ready folder. Never handles images, rendering or publishing.
- **Main Claude Code session:** images (images.py), rendering (tti_render.py), publishing, and calling tti-writer when new posts are needed.

## How topics were chosen
- Source: SE Ranking keyword metrics, US and UK databases, plus similar-keyword expansion.
- Tested patterns: best restaurants / places to eat / food / bars / rooftop bars / cocktail bars / brunch / cafes / street food / pubs in 40+ cities; day trips from; hidden gems; best beaches; islands; villages and small towns; weekend getaways; what to eat in; travel guides (for pillar keywords).
- Key findings: "things to do in [city]" is too hard everywhere (KD 43 to 98). Day trips are the best place format (KD around 5 to 8 with solid volume). "Best restaurants in [big city]" is mostly too hard; the "places to eat" and "food in" variants and second-tier cities are winnable. Bars are the best drink format.
- Variants for the same topic and place are merged into one post (e.g. restaurants + places to eat + food = one "Places to Eat" post; bars + cocktail bars = one post).
- Only keyword rows with KD 40 or under count towards a post's volume. Harder head terms are listed as stretch terms.
- Weighted KD = volume-weighted KD of counted rows. Winnability score = total US+UK volume / (KD + 10), multiplied by 0.25 if KD is over 35 or if the same keyword is KD 60+ in the other market.
- Topics under 100 combined monthly searches were dropped. Local/resident searches (suburbs, NJ, Tempe and similar) and point-to-point routes were excluded.
- Data flags: some SE Ranking volumes spiked recently (e.g. 10 to 590). These are flagged in content_plan.csv; re-check before prioritising.

## Duplicates and existing posts
- Existing city/country posts: Edinburgh, Brooklyn, Peru, Sapa, Hue, Tokyo, NYC, London, Chicago (incl. restaurants and pizza), Amsterdam, Barcelona, Athens, Norway, Argentina, Chile, China, Japan, Utah, California, USA, New Zealand, Manhattan, Ninh Binh, Thailand, Portugal, NYC art galleries, Instagrammable cafes, UK, Vietnam.
- Live UK posts to interlink: Top 10 Castles to Visit in the UK, Top 10 Historic Places in the UK, Top 10 Hidden Gems in the UK (so "Hidden Gems in the UK" was removed from the plan), Top 10 Weekend Getaways in the UK, Top 10 Coastal Destinations in the UK.
- A newer batch of 20 posts went live recently (including things to do in Lisbon and Algarve beaches). Check the site and folders for overlap before writing; e.g. Day Trips from Lisbon may overlap a Lisbon things-to-do post.

## Pillar and cluster structure
- Region hub > Country hub > City hub > listicle spokes. A place with 3+ spokes gets a city hub; smaller places roll up to their country hub or the region hub.
- Clusters within each hub: Eat, Drink, Explore nearby, See & do, Beaches & islands, Towns, villages & nature.
- Existing posts act as hubs where they fit: UK (parent of England, Scotland, Wales), Vietnam (parent of Hanoi and Ho Chi Minh City), Japan (parent of Tokyo, Osaka, Kyoto), USA, Thailand, Portugal, Peru, plus city posts for Edinburgh, London, Tokyo, NYC, Chicago, Amsterdam, Barcelona and Athens.
- Internal linking will be done as a separate pass later.

## Post standard
- 2,500 to 3,000 useful words (older posts median about 4,300; the first 20 new posts were too thin at about 1,400).
- 10 items, each with a practical box: How to get there / How long to spend / Best time to go / Tip.
- Supporting sections: how to pick, 1/2/3-day plans, getting around, where to stay by area, budget tiers. Food posts add a dishes glossary and booking/tipping notes.
- 5 or 6 FAQs from real searches.
- House rules: no em or en dashes, UK spelling, no exact prices, no made-up first-hand stories. Facts checked against official sources; unconfirmed facts left out.

## Batch 1 status (drafts-batch-1/)
Ten drafts written in Claude chat. They use `![alt](photo:slug)` placeholders and "Photo: credit on Unsplash" lines, which the image workflow should replace or strip. Frontmatter fields were guessed and need mapping to BLOG_TEMPLATE.md.
- Day Trips from Edinburgh: partly fact-checked (ScotRail Borders Railway, Rosslyn Chapel, Linlithgow Palace). About 4,000 words.
- The other nine (Copenhagen eat, Tokyo, Lisbon day trips, Lisbon eat, London, Amsterdam, Budapest eat, Osaka eat, Munich beer halls) are NOT yet fact-checked. The notes column in content_plan.csv lists what to check for each.

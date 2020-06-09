- [X] Initial Netlify migration

	- [X] Add `CHANGELOG.md`
	- [X] Add `.gitignore`
	- [X] Add `Gemfile`
	- [X] Migrate to Netlify-style redirects
	- [X] Migrate to Netlify-style build infrastructure
	- [X] Separate member data from page
	- [X] Clean up unused files
	- [X] Add as many (populated) RSS feeds as I can find
	- [X] Add member RSS feeds to header
	- [X] Create list of writings (from RSS feeds)
	- [X] Rename `members.md` to `members.html` to match content
	- [X] Add RSS and JSON feeds for writings category
	- [X] Create reusable "member card" widget
	- [X] Fix missing footer on homepage
	- [X] Update `README.md` to reflect changes
	- [X] Remove webhook reference (denial of service risk)

- [X] Integrate this repo into the main site

	- [X] Get current site into Netlify
	- [X] Swap DNS over to Netlify
	- [X] Reach out to members and make sure that RSS feeds are correct
	- [X] Merge this repo into current site

- [X] Redesign projects page

	- [X] Greenlit projects with tentative launch dates, stub "comming soon" pages
	- [X] Figure out how to lightly theme each project so that it has more of its own identity

- [X] Finish regularizing formatting, cleaning up unnecessary files/classes/divs, etc.

- [X] More fully document what different includes and data files do

- [X] Move `members.yml` data structure into member _pages_ listing projects they've participated in and recent posts

	- Member lookup will need to be indirect, through `site.categories["members"] | where: "id", "/members/venkatesh-rao"`, etc.
	- How to handle the creation of `yak-planet.ini`????
	- All member names should be links pointing to this page.
		- Should this apply to the member page itself?
		- How should the member page be linked back to?

- [X] Move to a more warren-like structure?

	- ~~No navigation~~, more in-page links
	- ~~Heavy use of tagging for projects?~~
	- ~~Can we figure out how to auto-tag incoming posts from feeds? Maybe some sort of light keyword-based classification? (This is another argument for moving to Gatsby, as this will probably be easier to implement there.)~~
	- Create links between members and all of their posts/projects.
	- Use member and home pages as hubs/entrances.

- [X] Figure out how to make site friendly for non-technical updates (this almost certainly means migrating to another platform)

	- ~~Migrate to Hugo and use a data file directory stored in Dropbox or Google Drive? Probably simplest, but least flexible long-run.~~
	- Spin up NetlifyCMS.
		- I increasingly like this idea, especially if `members.yml` can be broken into individual pages.
		- Will require people to have a GitHub account... (Bug? Feature?)
		- I think we'll want to use an "editorial approval" workflow, just to make sure that bad changes don't get pushed to the live site.
	- ~~Migrate to Gatsby and push user-editable files into Google Drive or Dropbox? Not clear how to do this within a dev/prod setup. (But maybe we don't care?)~~

- [X] Use Glitch to create posts from member feeds

	- See: https://webrender.net/2017/11/23/automate-github-pages-ifttt-glitch.html
	- No need for daily rebuild anymore...
	- Run Planet Pluto one last time to "seed" `writings/_posts/*`

- [X] [Create a _Join Us_ page](https://discordapp.com/channels/692111190851059762/704369362315772044/718228461684260944)

- [X] Migrate Glitch script to Netlify [serverless functions](https://docs.netlify.com/functions/overview/)

	- https://github.com/DavidWells/netlify-functions-workshop#workshop-lessons
	- https://www.trysmudford.com/blog/making-the-static-dynamic-instagram-importer/
	- https://github.com/netlify/netlify-lambda
	- https://github.com/rretsiem/renem.net/blob/master/src/functions/flickr-webhook.js
	- https://docs.netlify.com/configure-builds/file-based-configuration/

- [ ] Infrastructure housekeeping

	- [X] Update `README.md`
	- [ ] Move this list into Roam to encourage collaboration/ideas/etc.

		- This should also include a "how to" for editing files.

	- [ ] Formally add a GitHub issue tracker, link to Roam. See [this](https://discordapp.com/channels/@me/707243573061353472/709852606096212048) and [this](https://discordapp.com/channels/@me/707243573061353472/709881527642620046).
	- [ ] Figure out a better way to share logins for Yak Collective infrastructure.
	- [ ] Schedule office hours, walk interested folks through the site changes.

- [ ] Migrate [onboarding document](https://docs.google.com/document/d/1I63ZKu8o0DpBG0tWhssIsCinlXeBKO-xGyvmIMXXAWE/) into website (per [Venkatesh Rao](https://discordapp.com/channels/692111190851059762/692826420191297556/709550901555363861)).

	- If it's not already in there, it seems like the [code of conduct](https://roamresearch.com/#/app/ArtOfGig/page/i92e8kE2x) should probably be added, and then explicitly linked from `join.md` and `welcome.md` (rather than continuing to link to Roam).

- [ ] Figure out some kind of services / how to engage with us / contact us page. (How to do this while still being individual-member-centric?)

- [ ] Figure out how to post to Twitter when generating a "writings" post

- [ ] Figure out how to integrate feed list into the Netlify function, rather than using IFTTT

	- This needs to be user-editable!

- [ ] Rotating slogans

	- https://discordapp.com/channels/692111190851059762/712112363566006322/719654392327962643 (etc.)
	- JavaScript (per page load)? Or randomized includes (per build)?
		- Kinda inclined to go with randomized builds, as I so strongly dislike JavaScript.

- [ ] Additional member info ideas:

	- [ ] Add facility for tagging member skills
	- [ ] Add facility for [project-related badges](https://discordapp.com/channels/692111190851059762/708772535172333618/711625982473404436) on member cards and profile pages
		- Need to figure out what this will look like.
	- [ ] Personal archetype?

- [ ] Figure out how to automate some sort of mailing list

	- Bootstrap off of existing feed page
	- Pull notes from Roam (how? which ones?)
	- Push to Substack (how?) or Mailchimp (Mandrill API?)
	- Minimal/no human curration
	- [Reference idea](https://discordapp.com/channels/692111190851059762/692847835766325386/708707475117047910) (Nathan Acks/Darren Kong)

- [ ] Figure out how to integrate the Yak Collective Twitter list?

	- Maybe (probably?) just use the Glitch automation for this.
	- Also extend to Facebook, etc.
	- Or, maybe reverse? YC.org to Twitter, LinkedIn, etc.

- [ ] Engage with an actual designer to help with accessibility

	- [ ] Figure out how to support both light and dark OS color schemes using [`prefers-color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)

		- This is a lot more complicated than you'd think, what with header images, accent colors, etc.
		- We probably need help from someone who, you know, actually has some web design experience.

- [ ] Revisit use of Google Analytics on the site (some folks on Discord have expressed GDPR worries)